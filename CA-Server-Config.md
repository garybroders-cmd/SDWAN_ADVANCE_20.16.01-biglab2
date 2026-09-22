Make the Cisco router a CA Server automatically issue certificates</r>

crypto key gen rsa label PKI mod 2048</r>
crypto pki server PKI</r>
database url flash:</r>
database level complete</r>
issue-name cn=root.cloud1.local</r>
hash sha256</r>
database archive pkcs12 password Cisco!23</r>
grant auto</r>
no shut</r>

! Enter into configuration mode to pull of the root certificate
config t</r> 
! export the root CA certificate to paste into VManager</r>
crypto pki export PKI pem terminal pem</r>
