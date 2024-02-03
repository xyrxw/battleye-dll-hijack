# batlleye-dll-hijack
** its not mine. just a repost

there is a dll hijack possibility in beservice.exe which is responsible from checking certificates for modules loaded into the game.
the dll gets loaded VERY early. im pretty sure its one of the very few hijackable dlls.
make sure to load the original and redirect functions (look up "proxy dll generator").

hijack path: C:\Program Files (x86)\Common Files\BattlEye\MSASN1.dll

a bypass using this would be:
1. hijack the dll to get into beservice.exe
2. from there, hook "CryptSIPVerifyIndirectData" in crypt32.dll to always return true
3. now dll hijack into the game. your unsigned dll will be loaded due to the hook.

(!!!) warning: the bypass described above will most likely get you detected unless you somehow hide your module after its being loaded
this post is NOT meant to be a complete "bypass". its just information for learners to use for their own research.
its a way for researchers to analyze beservice from within without having to worry about beservice.exe being protected by bedaisy.


