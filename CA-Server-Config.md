Make the Cisco router a CA Server automatically issue certificates quickly guide</br>

crypto key gen rsa label PKI mod 2048</br>
crypto pki server PKI</br>
database url flash:</br>
database level complete</br>
issuer-name cn=root.cloud1.local</br>
hash sha256</br>
database archive pkcs12 password Cisco!23<b/r>
grant auto</br>
no shut</br>

! Enter into configuration mode to pull of the root certificate</br>
config t</br> 
! Export the root CA certificate to paste into VManager</br>
crypto pki export PKI pem terminal pem</br>


<b>To generate a signed certificate create CSR on the vmanage device or any device in attached to VManager</br>
<b>Goto the CA-Server and and run the following command below</br>

crypto pki server PKI request pkcs10 terminal</br>

<b>Paste your generateed CSR into the VMnanger</br>
<b>enter quit</br>
<b>then copy and paste your certicate into the vmanger install certificate location</br>

