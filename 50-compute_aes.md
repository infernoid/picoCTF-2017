## computeAES [50 Points]

You found this clue laying around. Can you decrypt it?

**Hints:**

- Try online tools or python

**Solution:**

Decrypt the base64 encoded key and ciphertext
and decrypt the AES ecrypted ciphertext with python
computeAES.py:

```python
#Encrypted with AES in ECB mode. All values base64 encoded
from Crypto.Cipher import AES

ciphertext = 'V3Vqirostg6qW26sle5mnyrwEYSrteN6oHkilO50e9dFkN+0JhC3yu0LcQNw/hXU'
key = 'r7y1dhmTvjQrcra7A1UQFw=='

decryptor = AES.new(key.decode('base64'), AES.MODE_ECB)
print decryptor.decrypt(ciphertext.decode('base64'))
```

```
$ python computeAES.py
flag{do_not_let_machines_win_6a68a292}__________
```

**Flag:** do_not_let_machines_win_6a68a292
