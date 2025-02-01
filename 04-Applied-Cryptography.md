# Schneier 2015: Applied Cryptography

## Foundational concepts in cryptography 

### Sender and Receiver: 
In secure communication, a sender wishes to securely deliver a message to a recipient. 
Ensuring that the communication cannot be read by prospective eavesdroppers is the sender's aim.


### Communication and Encryption:
  - Message: The communication's initial content, also known as cleartext or plaintext.
  - Encryption is the process of hiding the content of a plaintext message and rendering it unreadable by unauthorized parties.
  - Encrypted Message: Also referred to as ciphertext, this is the output of the encryption process.
  - Decryption: Restoring the ciphertext to its orignal plaintext form is known as decryption.

### Cryptography: 
The study of communication security via encryption.

### Crptographers: 
People who practice cryptography are known as cryptographers.

### Cryptanalysis 
Is the study and activity of deciphering encrypted messages; cryptanalysts usually carry out this task. 
This is figuring out how to decode the ciphertext without knowing the decryption key.

### Cryptology
The more general field that includes cryptanalysis and cryptography is called cryptology. 
Those who specialize in cryptology are known as cryptologists, and they frequently have theoretical mathematics training.

### Plaintext: 
The original, unencrypted message is represented by symbols like M or P. It can be text, pictures, or digital data, among other formats.


# Disobey 2023 conference

## Cyber Security is everyone's business - Lotta Sandroos

In order to encourage improved cyber security behavior, the presentation "Cyber Security: 
It's Everyone's Business" underlines the significance of addressing home users' cyber security concerns and the necessity of efficient communication techniques. 
The speaker states in their introduction that they have experience in both social sciences and cyber security. 
Their discussion, which is aimed at private individuals, is based on their master's thesis on cyber security communication.

- Among the presentation's main ideas are:

### Human mistake in Cyber Security: 
She highlights that people are frequently seen as the weakest link in cyber security and explains how social engineering and human mistake are frequent means for attackers to obtain access to sensitive data.

### Emphasis on Home Users: 
Despite a large body of study on the behavior of cyber security in corporate environments, home users have received less attention. 
Nonetheless, home users frequently lack the knowledge and assistance needed to protect themselves from the growing number of cyberthreats.

### Communication Strategies: 
The speaker makes the argument that, despite being prevalent, fear-based strategies in cyber security communication might not always be successful in encouraging behavior change. 
Rather, there ought to be a harmony between drawing attention to the dangers and offering suport and confidence in oneself.

### Social Marketing Strategy: 
She suggests utilizing a social marketing strategy to encourage changes in cyber security behavior. 
This provides incentives or advantages in return for adopting safe practices, such making use of password managers.

### Targeted Content and Education: 
The speaker proposes creating targeted content depending on people's backgrounds and ability levels, acknowledging that one-size-fits-all strategies might not work. 
This could involve more individualized outreach and instruction.

### Regulation and Responsibility: 
The presentation proposes that service providers should take on a more significant role in educating home users about cyber security. 
It also raises problems regarding who is ultimately liable for this. 
The speaker also makes a suggestion about potential future regulations in this field.


# Encrypt and decrypt a message

1st get updates
($ sudo apt-get update)

![image](https://github.com/Ruwan0127/rumarkdown/assets/144318600/7adebb40-3685-4b4e-88e7-3ddf3d3e1c87)

Then gpg encription tool is installed
($ sudo apt-get install gpg micro psmisc)

![image](https://github.com/Ruwan0127/rumarkdown/assets/144318600/cdb7f6be-4ff9-4db0-a972-17cf03f3dffa)


Then key pair is generated.
($ gpg --gen-key)
I did not protect the key with password. I left it empty (twice)

![image](https://github.com/Ruwan0127/rumarkdown/assets/144318600/e6a73288-0d66-4bfd-9fb4-00680c944fd3)

![image](https://github.com/Ruwan0127/rumarkdown/assets/144318600/01bc574c-dd0d-4650-98e9-debeda0b3091)


Now I have a keypair. I have picked only interesting lines of the output.

![image](https://github.com/Ruwan0127/rumarkdown/assets/144318600/4e59ebec-9863-401a-855e-3c917adfd3a7)

## Export My Public Key

I used the following code 
($ cd
$ gpg --export --armor --output ruwan.pub)

Then I have the public key

![image](https://github.com/Ruwan0127/rumarkdown/assets/144318600/62786e61-e3a3-4116-9cd8-8e63708b802f)


## Nilu, Simulated

Directory Nilu is created
($ cd
$ mkdir Nilu/
$ chmod og-rwx Nilu/)

![image](https://github.com/Ruwan0127/rumarkdown/assets/144318600/4e124410-e141-4ffd-87d4-3d9b0548a491)

To simulate Nilu, we can just work inside this folder, and replace 'gpg' with 'gpg --homedir .' 
This way, Nilu has her own settings and own keyring, separate from the one we actually use

![image](https://github.com/Ruwan0127/rumarkdown/assets/144318600/3766181f-75b5-46f8-a8fa-2ba45b73b137)


It's time for Nilu to create her own keypair.
($ gpg --homedir . --gen-key)

![image](https://github.com/Ruwan0127/rumarkdown/assets/144318600/811b3fc3-41b9-428b-a235-694b0f930701)


Nilu imports and verifies Ruwan's Key
($ cd
$ cp -v ruwan.pub Nilu/)

![image](https://github.com/Ruwan0127/rumarkdown/assets/144318600/62e90db2-ac2d-4083-97ce-77d70ef3a070)


Nilu can check the fingerprint to verify that this is indeed Ruwan's key.
($ gpg --homedir . --fingerprint)

![image](https://github.com/Ruwan0127/rumarkdown/assets/144318600/e8746588-f7a6-453f-a145-e31f64039e1b)

Nilu signs ruwan's key to mark it as trusted.

![image](https://github.com/Ruwan0127/rumarkdown/assets/144318600/2cd09d25-9d13-44ba-a8ae-357e54c7563d)

Keys could also be verified using singatures from trusted third parties. (ignore the 2nd one)

![image](https://github.com/Ruwan0127/rumarkdown/assets/144318600/179b1935-55b7-461f-95f7-d687188bf34b)


## Ruwan needs Nilu's Public Key to Know It's Her

Nilu wants to sign her messages. ruwan needs Nilu's key to know that it's really her.

Nilu:
($ gpg --homedir . --export --armor --output alice.pub
$ cp -v alice/alice.pub .)

![image](https://github.com/Ruwan0127/rumarkdown/assets/144318600/f2654488-7a07-47aa-a7dd-1261d3418ea5)

Key is sent over untrusted channel and ruwan imports the key
($ cd 
$ cp -v Nilu/Nilu.pub .
$ gpg --import Nilu.pub)

![image](https://github.com/Ruwan0127/rumarkdown/assets/144318600/affc9529-526e-4cf1-8bc2-2d98cbe6146e)

Then verify fingerprint...
($ gpg --sign-key "B20F D80B 705C 791D C878  0030 7BAA 4F13 2645 134F")

![image](https://github.com/Ruwan0127/rumarkdown/assets/144318600/255f430e-e439-45f2-8be8-3b4304db01f9)

![image](https://github.com/Ruwan0127/rumarkdown/assets/144318600/cc1c26e3-8a0e-4dc8-92b1-dfb6dbbd2ce2)

### Trust Established


# Nilu Sends a Secret Message

Nilu writes a message 
($ cd ~/alice/
$ micro message.txt)

Nilu's message

![image](https://github.com/Ruwan0127/rumarkdown/assets/144318600/9e1a6262-9900-43d4-a2f1-d69adff3ac81)

Then save by Ctrl-S and quit by Ctrl-Q.

She encrypts and signs the message

($ gpg --homedir . --encrypt --recipient ruwan@example.com.invalid --sign --output encrypted.pgp --armor message.txt)

![image](https://github.com/Ruwan0127/rumarkdown/assets/144318600/5d7991a4-5fa3-45d6-8ef4-12de06218ca7)

## Ruwan Decrypts and Verifies the Message

![image](https://github.com/Ruwan0127/rumarkdown/assets/144318600/8753156b-74d7-464f-8f4e-00d4ba512453)

Nilu's signature was verified using Nilu's public key.



# ETAOIN. 

## Crack this ciphertext:

HDMH'B TH. 
KWU'YI AWR WSSTOTMJJK M OWQINYIMLIY! MB KWU BII, 
BTGPJI BUNBHTHUHTWA OTPDIYB OMA NI NYWLIA RTHD SYIEUIAOK MAMJKBTB. 
BII KWU MH DHHP://HIYWLMYCTAIA.OWG

- The frequency table is ETAOIN, means that the most common letter in inglish is E and then T and so on. 
- By looking at this I realized that
    - 'B as 'S
    - DHHP: should be HTTP ,
          - so D = H, H = T, P = P
    - .OWG is .COM ,
          - so O = C , W = O , G = M

So now the message looks like this ( I used simple letters to identified ones)

thMt's Tt. 
KoU'YI AoR oSSTcTMJJK M coQINYIMLIY! Ms KoU sII, 
sTGpJI sUNstTtUtToA cTphIYs cMA NI NYoLIA RTth SYIEUIAcK MAMJKsTs. 
sII KoU Mt http://tIYoLMYCTAIA.com

  - thMt's Tt, should be "that's it".
    - so M = A , T = I

that's it. 
KoU'YI AoR oSSiciaJJK a coQINYIaLIY! as KoU sII, 
siGpJI sUNstitUtioA ciphIYs caA NI NYoLIA Rith SYIEUIAcK aAaJKsis. 
sII KoU at http://tIYoLaYCiAIA.com

   - sII will be "see"
    - so I = E
  - KoU should be "you"
      - so K = Y and U = U
  - 'Ye is 're
      - so Y = R

that's it. 
you're AoR oSSiciaJJy a coQeNreaLer! as you see, 
siGpJe suNstitutioA ciphers caA Ne NroLeA Rith SreEueAcy aAaJysis. 
see you at http://teroLarCiAeA.com 

  - caA should be "can"
    - so A = N
  - then AoR will be "now"
    - so R = W
  - Ne is "be"
      - so N = B
  - oSSiciaJJy = = "officially"
      so S = F, J = L

that's it. 
you're now officially a coQebreaLer! as you see, 
siGple substitution ciphers can be broLen with freEuency analysis. 
see you at http://teroLarCinen.com   

  - siGple is "simple"
    - so G = M   
  - coQebreaLer is "codebreaker"
     - so Q = D and  L = K
  - freEuency is "frequency"
     - so E = Q 
  - teroLarCinen = "terokarvinen"
      so C = V
    
### so I revealed the message      
that's it. 
you're now officially a codebreaker! as you see, 
simple substitution ciphers can be broken with frequency analysis. 
see you at http://terokarvinen.com

## References

1.https://learning.oreilly.com/library/view/applied-cryptography-protocols/9781119096726/08_chap01.html#chap01-sec006
2.https://www.youtube.com/@Disobey/videos
3.https://www.youtube.com/watch?v=FGcC0ZirfVY
4.https://terokarvinen.com/2023/pgp-encrypt-sign-verify/ 
