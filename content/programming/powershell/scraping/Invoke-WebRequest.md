---
title: "Invoke-WebRequest"
draft: false
---

Source: https://docs.microsoft.com/en-us/powershell/module/Microsoft.PowerShell.Utility/Invoke-WebRequest?view=powershell-5.1
{{% panel="Invoke-WebRequest" header="Invoke-WebRequest" theme="default" %}}

Invoke-WebRequest is one of the most important modules for OSINT with powershell. You can read this same documentation in the command line by typing ```Get-Help Invoke- WebRequest -Examples``` it has been cleaned up for easy readability here.

```bash
# Invoke-WebRequest
      [-Uri] <Uri>
      [-Body <Object>]
      [-Certificate <X509Certificate>]
      [-CertificateThumbprint <String>]
      [-ContentType <String>]
      [-Credential <PSCredential>]
      [-DisableKeepAlive]
      [-Headers <IDictionary>]
      [-InFile <String>]
      [-MaximumRedirection <Int32>]
      [-Method <WebRequestMethod>]
      [-OutFile <String>]
      [-PassThru]
      [-Proxy <Uri>]
      [-ProxyCredential <PSCredential>]
      [-ProxyUseDefaultCredentials]
      [-SessionVariable <String>]
      [-TimeoutSec <Int32>]
      [-TransferEncoding <String>]
      [-UseBasicParsing]
      [-UseDefaultCredentials]
      [-UserAgent <String>]
      [-WebSession <WebRequestSession>]
      [<CommonParameters>]
```

```powershell
# Get all links
(Invoke-WebRequest -Uri "http://msdn.microsoft.com/en-us/library/aa973757(v=vs.85).aspx").Links.Href
```

```powershell
$R = Invoke-WebRequest -URI http://www.bing.com?q=how+many+feet+in+a+mile
$R.AllElements | where {$_.innerhtml -like "*=*"} | Sort { $_.InnerHtml.Length } | Select InnerText -First 5
innerText---------1 =5280 feet1 mile
```

```powershell
# The first command uses the **Invoke-WebRequest** cmdlet to send a sign-in request. The command specifies a value of "FB" for the value of the *SessionVariable* parameter, and saves the result in the $R variable.When the command completes, the $R variable contains an **HtmlWebResponseObject** and the $FB variable contains a **WebRequestSession** object.

$R=Invoke-WebRequest http://www.facebook.com/login.php -SessionVariable fb
```

```powershell
# The second command shows the **WebRequestSession** object in the $FB variable.

$FB
```
```powershell
# The third command gets the first form in the **Forms** property of the HTTP response object in the $R variable, and saves it in the $Form variable.

$Form = $R.Forms[0]
```

```powershell
# The fourth command pipes the properties of the form in the $Form variable into a list by using the Format-List cmdlet.
$Form | Format-List
```

```powershell
# The fifth command displays the keys and values in the hash table (dictionary) object in the Fields property of the form.

$Form.fields
```
```powershell
# The sixth and seventh commands populate the values of the email and pass keys of the hash table in the **Fields** property of the form. You can replace the email and password with values that you want to use.

$Form.Fields["email"]="User01@Fabrikam.com"
$Form.Fields["pass"]="P@ssw0rd"
```

```powershell
# The eighth command uses the **Invoke-WebRequest** cmdlet to sign into the Facebook web service.The value of the *Uri* parameter is the value of the **Action** property of the form. The **WebRequestSession** object in the $FB variable (the session variable specified in the first command) is now the value of the *WebSession* parameter. The value of the *Body* parameter is the hash table in the Fields property of the form and the value of the *Method* parameter is POST. The command saves the output in the $R variable.

$R=Invoke-WebRequest -Uri ("https://www.facebook.com" + $Form.Action) -WebSession $FB -Method POST -Body $Form.Fields
```

```powershell
# The full script, then, is as follows.
# Sends a sign-in request by running the Invoke-WebRequest cmdlet. The command specifies a value of "fb" for the SessionVariable parameter, and saves the results in the $R variable.

$R=Invoke-WebRequest http://www.facebook.com/login.php -SessionVariable fb
```

```powershell
# Use the session variable that you created in Example 1. Output displays values for Headers, Cookies, Credentials, etc. 

$FB
```

```powershell
# Gets the first form in the Forms property of the HTTP response object in the $R variable, and saves it in the $Form variable. 

$Form = $R.Forms[0]
```

```powershell
# Pipes the form properties that are stored in the $Forms variable into the Format-List cmdlet, to display those properties in a list. 

$Form | Format-List
```

```powershell
# Displays the keys and values in the hash table (dictionary) object in the Fields property of the form.

$Form.fields
```

```powershell
# The next two commands populate the values of the "email" and "pass" keys of the hash table in the Fields property of the form. Of course, you can replace the email and password with values that you want to use. 

$Form.Fields["email"] = "User01@Fabrikam.com"
$Form.Fields["pass"] = "P@ssw0rd"
```

```powershell
# The final command uses the Invoke-WebRequest cmdlet to sign in to the Facebook web service. 

$R=Invoke-WebRequest -Uri ("https://www.facebook.com" + $Form.Action) -WebSession $FB -Method POST -Body $Form.Fields
```

```powershell
# When the command finishes, the **StatusDescription** property of the web response object in the $R variable indicates that the user is signed in successfully.

$R.StatusDescription
```
{{% /panel %}}