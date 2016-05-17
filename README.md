# go-ntlm-auth

This is an implementation of NTLM for Go that was implemented using Windows SSPI (Security Support Provider Interface).
It differs from other implemenations of NTLM as it uses the Default Credentials of the account that the application runs with. 
Therefore username and password does not have to be provided. 

## Usage Notes:
Currently the implementation only supports Windows. We didn't need it for Linux, so we haven't implemented it yet. 

In order to perform NTLM Http Request by invoking ntlm.DoNTLMRequest(client, req) passing in http client and http request.

### References:
https://github.com/denisenkom/go-mssqldb - we used sspi_windows.go source file to perform Win32 calls to SSPI
https://github.com/github/git-lfs/blob/master/lfs/ntlm.go - git-lfs uses thomson reuters implementation of ntlm, however we looked how it was all chained together and stripped of some code from it