# **!!!!!!!! WARNINGS !!!!!!!!**

## **THIS REPOSITORY CONTAINS MALWARES!!!! DON'T DOWNLOAD OR RUN ANYTHING IN IT UNLESS YOU CLEARLY UNDERSTAND WHAT YOU ARE DOING!!!!**

# **！！！！ 警告 ！！！！**

## **該目錄下存有病毒程式！！！！ 請不要嘗試下載或運行裡面的任何程式，除非你非常清楚你在幹什麼！！！！**

# DCM Virus Samples

DCM is a Trojan Spy-ware dedicated to APT attack of specific targets.
It's first disclosed by Tecent's security team on Freebuf.<sup>[\[1\]][1]</sup>
It's developed by Chinese agency which rumored to be some g0v related
people. A self-claimed author member "DcmTeamMember" on V2EX posted
the insights about the creation of the virus.<sup>[\[2\]][2]</sup>

This repository contains some samples of the DCM virus collected from
various online virus sharing channels. The naming is the file's MD5
hash. If the original file is packed (usually with UPX) then an unpacked
version is provided for convinence.

#### `278ce79753aaa050fe750baba43490e5`

**Report:** http://r.virscan.org/report/fee007c110eeb4dfdba508120ab6bef4

This is the exact version used in the analysis article on Freebuf. So
I will personally refer it as `DCM-0`.

The resource files in the unpacked executable is encrypted with simple
XOR algorithm. (implemented in `sub_4011C0`) I added a decryption
script for your convinence. The extracted and decrypted resource files
are also included.

#### `1b7cd62b71235443cf267bd9104679dd`

**Report:** https://totalhash.cymru.com/analysis/?fbbbc68a4b56c9c70487753be3c26f4293e79ec9

This version has the same program structure as `DCM-0`. Even the
resource files are encrypted with the same algorithm. However the binary
seems to be a slightly larger than `DCM-0` thus I would guess it's an
upgraded version to `DCM-0`.

#### `261f4bbc423d79a1115840f300d5daf0`

**Report:** https://totalhash.cymru.com/analysis/?30161f778c28443b40b5cef76dc977b0c2c4c352

This version is another slightly changed `DCM-0`. It has less behaviour
characteristics on the report.

#### `89a5257fd9415b68ceab4a2122f70b45`

**Report:** https://totalhash.cymru.com/analysis/?823daa3fe3c32c32573b0317b488db901a191018

This version is basically the same as `DCM-0` with some minor changes.

#### `82304a0a2ab419f657a4e9d8319c1e99`

**Report:** https://totalhash.cymru.com/analysis/?6f31aa2d01c5a67744fa8688933ae31dfc5a9c0d

This sample is reported to create mutex named `Global\I_AM_EXIST!!`,
which is an identifier of the DCM behaviour. However it lacks of any
other behaviour that a typical DCM virus should has. Therefore I think
it's actually an early or experimental version of `DCM-0`. It even doesn't
encrypt its resource files.

#### `1b2f0cbd3f048ee9f3e9885d4076ce8c`

**Report:** https://home.mcafee.com/virusinfo/virusprofile.aspx?key=2236045

I believe it's an early version DCM virus due to the small file size,
and lack of most of the behaviour characteristics of `DCM-0`. However,
it does generate `%TEMP%\{E53B9A13-F4C6-4d78-9755-65C029E88F02}\soft.prog`
and other core files that we can be certain that it's a variation of DCM.
Unlike `82304a0a2ab419f657a4e9d8319c1e99`, this version uses XOR encryption
for its resource files, but is slightly different than the algorithm used
in `DCM-0` in terms of parameters. Thus I think it's a development upgrade
of `82304a0a2ab419f657a4e9d8319c1e99`.

[1]: http://www.freebuf.com/articles/system/101447.html
[2]: https://www.v2ex.com/t/271590
