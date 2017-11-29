# High Sierra root vulnerability validator

## Description

An attacker may be able to bypass administrator authentication without supplying the administrator’s password.

A logic error existed in the validation of credentials. This was addressed with improved credential validation.

CVE: [CVE-2017-13872](https://cve.mitre.org/cgi-bin/cvename.cgi?name=2017-13872)

Available for: macOS High Sierra 10.13.1

Not impacted: macOS Sierra 10.12.6 and earlier 

Source: [Apple Support](https://support.apple.com/es-lamr/HT208315)

## Usage

* Open the launchpad (F4) and find Terminal application
  
* Copy the following code in the console:
  
`payload=$(osascript -e 'do shell script "whoami" with administrator privileges user name "root" password ""');if [ "$payload" = "root" ] ; then echo -e "Vulnerable: Please update! \nMore info: https://support.apple.com/es-lamr/HT208315";else echo "Not Vulnerable";fi`

