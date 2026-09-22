Make the Cisco router a CA Server automatically issue certificates</br>

crypto key gen rsa label PKI mod 2048</br>
crypto pki server PKI</br>
database url flash:</br>
database level complete</br>
issue-name cn=root.cloud1.local</br>
hash sha256</br>
database archive pkcs12 password Cisco!23<b/r>
grant auto</br>
no shut</br>

! Enter into configuration mode to pull of the root certificate</br>
config t</ r> 
! export the root CA certificate to paste into VManager</br>
crypto pki export PKI pem terminal pem</br>
