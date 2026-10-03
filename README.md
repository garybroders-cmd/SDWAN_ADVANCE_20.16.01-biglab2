# Overview notes
updates:- 3/10/2026-</br>
2 Validators-</br>
3 controllers-</br>
8 vEdge Routers - to be configured-</br>
1 Linux DNS server-</br>

EVE-NG Pro 2026, 256GB RAM, 1.7 TB hard disk, 2.5GB-10 GB network.-</br>
Bare-metal install Ubuntu 24. x.x-</br>

Cisco SD-WAN devices 20.16.x and vEdges 17.16.01 worked best.-</br>





# Create Root CA and issue Certificates via Cisco Router


crypto key generate rsa label PKI 2048</r>

! enter into pki server and create database.</r>
crypto pki server PKI</r>

database url flash:</r>
database level complete</r>


issuer-name cn=root.cloud2.local.org</r>

hash sha256</br>
database archieve pkcs12 password C#####</br>
grant auto</r>
no shutdown</r>
wr mem</r>


cert-server#crypto pki server PKI request pkcs10 terminal</r>

%PKCS10 request in base64 or pem</r>

% Enter Base64 encoded or PEM formatted PKCS10 enrollment request.</r>
% End with a blank line or "quit" on a line by itself.</r>
% Paste your CSR from the SDWAN or vManager etc..</r>

-----BEGIN CERTIFICATE REQUEST-----<r>
MIIDSzCCAjMCAQAwgcoxCzAJBgNVBAYTAkdCMQ8wDQYDVQQIEwZMb25kb24xDzAN<r>
BgNVBAcTBkJhcm5ldDEPMA0GA1UECxMGc2R3YW4xMRAwDgYDVQQKEwdiaWdsYWIy<r>

cert-server#crypto pki server PKI request pkcs10 terminal<r>
PKCS10 request in base64 or pem<r>

% Enter Base64 encoded or PEM formatted PKCS10 enrollment request.</r>
% End with a blank line or "quit" on a line by itself.<r>
% paste your CSR here <r>
-----BEGIN CERTIFICATE REQUEST-----<r>
MIIDSzCCAjMCAQAwgcoxCzAJBgNVBAYTAkdCMQ8wDQYDVQQIEwZMb25kb24xDzAN</r>
BgNVBAcTBkJhcm5ldDEPMA0GA1UECxMGc2R3YW4xMRAwDgYDVQQKEwdiaWdsYWIy<r>
---truncated---<r>
ikM4tBLbEpgFfBZf0674wDp2FrdQstzEfWVJTJVHUQ==<r>
-----END CERTIFICATE REQUEST-----</r>
quit</r>

% Cut and paste the new certificate below </r>

% Granted certificate:</r>
-----BEGIN CERTIFICATE-----</r>
MIIDtjCCAp6gAwIBAgIBAzANBgkqhkiG9w0BAQsFADAdMRswGQYDVQQDExJyb290</r>
LmJpZ2xhYjIubG9jYWwwHhcNMjYwOTIwMTQzMDI1WhcNMjcwOTIwMTQzMDI1WjCB</r>
---truncated---</r>
81pDD9OTVixFmYxgzkCvuVnUHTAIhbeBtqNyUmxfrrnSWBbiGy3uG3TN</r>
-----END CERTIFICATE-----</r>

cert-server#</r>

cert-server#</r>
