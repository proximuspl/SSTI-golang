[Basics SSTI in GO](https://book.hacktricks.xyz/pentesting-web/ssti-server-side-template-injection#ssti-in-go) - hacktricks

# Bypass quotes
* Use `` ` `` instead of ``"``
for example
  * ``{{len `test`}}`` will render as "4"
 
  
# Bypass space
* Use new line characters (CR/LF/CRLF) for example 
  * HTTP GET ``/ssti.go?q={{len%0a%0d`test`}}`` will render as "4"
