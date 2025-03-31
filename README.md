
# YoinkLighter

A tool to create spoof code signing certificates in order to sign binaries and DLL files to aid in the intention to evade EDR products and minimize SOC scrutiny. 
YoinkLighter can also use valid code signing certificates to sign files. 
YoinkLighter can use a fully qualified domain name such as `acme.com`.
Additionally, YoinkLighter allows supports the ability to pilfer existing certificates from other binaries and embed icons.

## Contributing
YoinkLighter is a fork of the @Tylous LimeLighter GoLang project.
The intention was to utilize pure GoLang in order to perform portable executable (PE) manipulations. Whilst in theory th
Make sure that the following are installed on your OS 

```
openssl
osslsigncode
```

The first step as always is to clone the repo. Before you compile YoinkLighter you'll need to install the dependencies. To install them, run following commands:
```
go get github.com/savsanta/yoinkfuncs
go get github.com/fatih/color
go get github.com/charmbracelet/huh


```

Then build it

```
go build YoinkLighter.go
```




## Usage

```
./YoinkLighter -h       

_____.___.      .__        __   .____    .__       .__     __                
\__  |   | ____ |__| ____ |  | _|    |   |__| ____ |  |___/  |_  ___________ 
 /   |   |/  _ \|  |/    \|  |/ /    |   |  |/ ___\|  |  \   __\/ __ \_  __ \
 \____   (  <_> )  |   |  \    <|    |___|  / /_/  >   Y  \  | \  ___/|  | \/
 / ______|\____/|__|___|  /__|_ \_______ \__\___  /|___|  /__|  \___  >__|   
 \/                     \/     \/       \/ /_____/      \/          \/                                                               
                                            @Savsanta


[*] A Tool for Code Signing... Real or Fake
Usage of ./YoinkLighter:
  -Domain string
        Domain you want to create a fake code sign for
  -I string
        Unsigned file name to be signed
  -O string
        Signed file name
  -S string
        Path to an existing EXE to steal resources from
  -Password string
        Password for real  certificate
  -Real string
        Path to a valid .pfx certificate file
  -Verify string
        Verifies a file's code sign certificate
  -debug
        Print debug statements

```

To sign a file you can use the command option `Domain` to generate a fake code signing certificate.

![Signing](Screenshots/Signing.png)

to sign a file with a valid code signing certificate use the `Real` and `Password` to sign a file with a valid code signing certificate.


To verify a signed file use the `verify` command.

![Verifying](Screenshots/Verifing.png)
![WindowsVerifying](Screenshots/WindowsVerifying.png)
