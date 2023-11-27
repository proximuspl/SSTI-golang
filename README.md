[Basics SSTI in GO](https://book.hacktricks.xyz/pentesting-web/ssti-server-side-template-injection#ssti-in-go) - hacktricks

# Bypass quotes
* Use `` ` `` instead of ``"``
for example
* ``{{len `test`}}`` will render as "4"
