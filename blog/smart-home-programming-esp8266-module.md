---
title: "Smart Home – Programming ESP8266 Module"
description: "Assuming your module is already armed with the NodeMCU firmware, its time to program our end point so we could control it remotely through wifi. In our case at the moment, we simply need to control one of its output PIN to give out power ( Switch on / off ) depending on the signals […]"
pubDate: 2017-01-17
category: "Randoms"
tags: []
draft: false
---
<p>Assuming your module is already armed with the NodeMCU firmware, its time to program our end point so we could control it remotely through wifi. In our case at the moment, we simply need to control one of its output PIN to give out power ( Switch on / off ) depending on the signals we send through our home bridge device.</p>
<p>An easy way to do this is to run a small webserver on our ESP module and set few url&#8217;s to control our output. In our case we just need two unique url&#8217;s to switch on and off. Or we can also create a more generic url which we can pass on PIN numbers and STATUS to switch on and off. but that seems unnecessarily open and i&#8217;d prefer to have pre defined urls according to the need.</p>
<p>Its time to start programming our module. Assuming you already have <a href="http://esp8266.ru/download/esp8266-doc/Getting%20Started%20with%20the%20ESPlorer%20IDE%20-%20Rui%20Santos.pdf" target="_blank">ESPlorer</a> application and its all setup to communicate with your device, lets insert the following lua code in to the ESP module.</p>
<p>&nbsp;</p>
<pre class="brush: bash; title: ; notranslate">
wifi.setmode(wifi.STATION)
wifi.sta.config(&quot;WIFI_SSID&quot;,&quot;WIFI_PASSWORD&quot;)
led1 = 0
gpio.mode(led1, gpio.OUTPUT)
srv=net.createServer(net.TCP)
srv:listen(80,function(conn)
    conn:on(&quot;receive&quot;, function(client,request)
        local buf = &quot;&quot;;
        local _, _, method, path, vars = string.find(request, &quot;([A-Z]+) (.+)?(.+) HTTP&quot;);
        if(method == nil)then
            _, _, method, path = string.find(request, &quot;([A-Z]+) (.+) HTTP&quot;);
        end
        local _GET = {}
        if (vars ~= nil)then
            for k, v in string.gmatch(vars, &quot;(%w+)=(%w+)&amp;*&quot;) do
                _GET[k] = v
            end
        end
        buf = buf..&quot;

&lt;h1&gt; ESP8266 Web Server&lt;/h1&gt;


&quot;;
        buf = buf..&quot;

GPIO0 &lt;a href=\&quot;?pin=ON1\&quot;&gt;&lt;button&gt;ON&lt;/button&gt;&lt;/a&gt;&amp;nbsp;&lt;a href=\&quot;?pin=OFF1\&quot;&gt;&lt;button&gt;OFF&lt;/button&gt;&lt;/a&gt;

&quot;;
        local _on,_off = &quot;&quot;,&quot;&quot;
        if(_GET.pin == &quot;ON1&quot;)then
              gpio.write(led1, gpio.LOW);
        elseif(_GET.pin == &quot;OFF1&quot;)then
              gpio.write(led1, gpio.HIGH);
        end
        --client:send(buf);
        client:close();
        collectgarbage();
    end)
end)
</pre>
<p>This is a temporary script i&#8217;ve written to test things out at the time of writing this posts. Incase i forgot to come back here and update, please get the latest codes from here <a href="https://github.com/nilansanjaya/smart-home/" rel="nofollow">https://github.com/nilansanjaya/smart-home/</a></p>
<p>When you are done sending that code to your ESP module, you should now be able to switch on and off its built in LED light using the below url&#8217;s ( Assuming you are connected to the same wifi network )</p>
<p><a href="http://youripaddress/?pin=ON1" rel="nofollow">http://youripaddress/?pin=ON1</a><br />
<a href="http://youripaddress/?pin=OFF1" rel="nofollow">http://youripaddress/?pin=OFF1</a></p>
<p>If that&#8217;s working, you can simply send requests to this through homebridge. Details on that should be on another post.</p>
