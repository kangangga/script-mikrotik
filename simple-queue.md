

```sh
{
local start "1";
local finish "20";
local upload "2M";
local download "2M";
local name "IP-5.";
local target "192.168.5.";
tonum $start;
tonum $finish;
for x from $start to $finish do={/queue simple add name="$name$x" max-limit="$upload/$download" target="$target$x"};
}
```