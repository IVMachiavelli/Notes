---
title: "Dig"
draft: false
---
{{% panel="Dig All Options" header="Dig All Options" theme="default" %}}
```bash
dig wired.com
```
<div align="center">
<script type="text/javascript" src="https://asciinema.org/a/upPQdo6yJ56S6GuGgfuZ5lepH.js" id="asciicast-upPQdo6yJ56S6GuGgfuZ5lepH" async></script>
</div>
{{% /panel %}}

{{% panel="Dig answer" header="Only Answer" theme="default" %}}
```bash
dig cnn.com +noall +answer
```
<div align="center">
<script type="text/javascript" src="https://asciinema.org/a/HEmSPVbawkZArZaaEFNQLmv0x.js" id="asciicast-HEmSPVbawkZArZaaEFNQLmv0x" async></script>
</div>
{{% /panel %}}


{{% panel="Just IP" header="Get IP Address of Domain" theme="default" %}}
```bash
dig outlook.com +short
```
<div align="center">
<script type="text/javascript" src="https://asciinema.org/a/PUWRUFTlBarUpNPqc5SiX1msG.js" id="asciicast-PUWRUFTlBarUpNPqc5SiX1msG" async></script>
</div>
{{% /panel %}}

{{% panel="Get Name Servers" header="Get Name Servers" theme="default" %}}
```bash
dig bbc.com ns +short
```
<div align="center">
<script type="text/javascript" src="https://asciinema.org/a/nkAGJc3NdsBW0MaowqtXHqSpj.js" id="asciicast-nkAGJc3NdsBW0MaowqtXHqSpj" async></script>
</div>
{{% /panel %}}

{{% panel="MX Records" header="MX Records" theme="default" %}}
```bash
 dig -t MX bloomberg.com +noall +answer
```
<div align="center">
<script type="text/javascript" src="https://asciinema.org/a/8i6c5XnRqU4Qxprp5X8RBIjB7.js" id="asciicast-8i6c5XnRqU4Qxprp5X8RBIjB7" async></script>
</div>
{{% /panel %}}

{{% panel="DNS Records" header="DNS Records" theme="default" %}}
```bash
dig github.com ANY +noall +answer
```
<div align="center">
<script type="text/javascript" src="https://asciinema.org/a/mtotUiUZj7548IO9Tm2zOdQtD.js" id="asciicast-mtotUiUZj7548IO9Tm2zOdQtD" async></script>
</div>
{{% /panel %}}

{{% panel="Reverse DNS" header="Reverse DNS" theme="default" %}}
```bash
dig -x 192.30.253.112 +noall +answer
```
<div align="center">
<script type="text/javascript" src="https://asciinema.org/a/XDX1nRQp8fG8ofDgdUiXNrOKY.js" id="asciicast-XDX1nRQp8fG8ofDgdUiXNrOKY" async></script>
</div>
{{% /panel %}}

{{% panel="Use Specific DNS Server" header="Use Specific DNS Server" theme="default" %}}
```bash
dig @ns3.msft.net microsoft.com
```
<div align="center">
<script type="text/javascript" src="https://asciinema.org/a/oMqjNV1Do4jlbEFXDi59hXyZZ.js" id="asciicast-oMqjNV1Do4jlbEFXDi59hXyZZ" async></script>
</div>
{{% /panel %}}

{{% panel="Dig from File" header="Dig from File" theme="default" %}}
```bash
dig -f dns-targets.txt +noall +answer && dig -f dns-targets.txt MX +noall +answer
```
<div align="center">
<script type="text/javascript" src="https://asciinema.org/a/nrYpVboV1uIXicG2vI5AlnloT.js" id="asciicast-nrYpVboV1uIXicG2vI5AlnloT" async></script>
</div>
{{% /panel %}}
