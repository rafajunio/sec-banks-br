# Security Analysis of Brazilian Banking on Android

We present a security analysis of eight Brazilian mobile banking applications in the Android platform, spanning more than 4 years. The scope included security aspects of the application, server configuration, and connection between app 
and server. We demonstrate impersonation attacks were possible against most banks, allowing an attacker to obtain sensitive data.

### The analyzed banks
- [![N|Solid](https://drive.google.com/uc?export=view&id=1AWsPYPXzUAY0hRgyrdJZL6FjkZQIGx1Z)](http://www.bb.com.br)**: Banco do Brasil** 
- [![N|Solid](https://drive.google.com/uc?export=view&id=1y3QzNla6ueCi8_T_wCCs6Qh-HL0mns5C)](https://banco.bradesco)**: Bradesco**
- [![N|Solid](https://drive.google.com/uc?export=view&id=1whKatLX_0TCsq6egDDzqocnPo9EuSqG_)](https://www.caixa.gov.br)**: Caixa Econômica Federal**
- [![N|Solid](https://drive.google.com/uc?export=view&id=1WsiqLEKwe23dzRSpQJsH3SiUk0CrbSIM)](https://www.citibank.com.br)**: Citibank**
- [![N|Solid](https://drive.google.com/uc?export=view&id=1IbrzPT2X8XfaJdRG4ZkxPze2bYiGzOzU)](https://www.hsbc.com.br/)**: HSBC**
- [![N|Solid](https://drive.google.com/uc?export=view&id=1LvZ7wDEmm46GepS13uFAIJKCKujGyKSh)](https://www.itau.com.br/)**: Itaú Unibanco**
- [![N|Solid](https://drive.google.com/uc?export=view&id=1k5QRxUaosz_GcJIUxa5mYLMGPjkBywAj)](https://www.nubank.com.br)**: Nubank**
- [![N|Solid](https://drive.google.com/uc?export=view&id=1a9MUNVfXu-_pwS7a7_QpOMnqCCA-x21a)](https://www.santander.com.br/)**: Santander**


### Tools used
Our attack environment supposed an Android smartphone connected to a wireless local network, where a malicious computer is also present. We use the following tools: 


| Tool | Description |
| ------ | ------ |
| [Wireshark](https://www.wireshark.org/) | Network protocol analyzer. |
| [APK Downloader](http://codekiem.com/2012/02/24/apk-downloader/) | Download APK files from Playstore to PC. |
| [dex2jar](https://github.com/pxb1988/dex2jar) | Work with android .dex and java .class files. |
| [JD-GUI](http://jd.benow.ca/) | Is a standalone graphical utility that displays Java source codes of ".class" files. |
| [arpspoof](http://www.monkey.org/~dugsong/dsniff) | Is a dsniff tool that makes ARP spoofing. |
| [OpenSSL](https://www.openssl.org) | OpenSSL is a robust, commercial-grade, and full-featured toolkit for the TLS and SSL protocols.  |
| [SSLsplit](https://www.roe.ch/SSLsplit) |  Transparent SSL/TLS interception.  |
| [Qualys SSL Labs](https://www.ssllabs.com) |  SSL Labs is a collection of documents, tools and thoughts related to SSL.  |


#### Command line to extract APKs files at Linux:
Inside each month folder you can use:

``$ gpg -q --batch --passphrase `echo GoogleBotPleaseDont` -o <apk_name> -d <apk_name>.gpg``

Example:

```
$ cd collects/09-december2019/apks
$ gpg -q --batch --passphrase `echo GoogleBotPleaseDont` -o BB_br.com.bb.android.apk -d BB_br.com.bb.android.apk.gpg
```


### Disclaimer
All apps are in original form without any modification and they are here for academic purposes only. Please do not distribute
