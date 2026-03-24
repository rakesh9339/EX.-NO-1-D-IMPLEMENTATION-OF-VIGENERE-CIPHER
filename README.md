# EX.-NO-1-D-IMPLEMENTATION-OF-VIGENERE-CIPHER



## AIM:
  To implement the Vigenere Cipher substitution technique using C program.
  
## ALGORITHM:
  STEP-1: Arrange the alphabets in row and column of a 26*26 matrix.
  
  STEP-2: Circulate the alphabets in each row to position left such that the first letter is attached to last.
 
  STEP-3: Repeat this process for all 26 rows and construct the final key matrix.
  
  STEP-4: The keyword and the plain text is read from the user.
  
  STEP-5: The characters in the keyword are repeated sequentially so as to match with that of the plain text.
  
  STEP-6: Pick the first letter of the plain text and that of the keyword as the row  indices and column indices respectively.
  
  STEP-7: The junction character where these two meet forms the cipher character.
  
  STEP-8: Repeat the above steps to generate the entire cipher text.
  
## PROGRAM:
```c
#include <stdio.h>
#include <string.h>
#include <ctype.h>

int main() {
    char text[100], key[100], cipher[100], decrypted[100];
    int i, j, len, keylen;

    printf("Enter plaintext: ");
    scanf("%s", text);

    printf("Enter keyword: ");
    scanf("%s", key);

    len = strlen(text);
    keylen = strlen(key);

    // Encryption
    for(i=0; i<len; i++) {
        char t = toupper(text[i]);
        char k = toupper(key[i % keylen]);
        cipher[i] = ((t - 'A') + (k - 'A')) % 26 + 'A';
    }
    cipher[len] = '\0';
    printf("Encrypted Text: %s\n", cipher);

    // Decryption
    for(i=0; i<len; i++) {
        char c = cipher[i];
        char k = toupper(key[i % keylen]);
        decrypted[i] = ((c - k + 26) % 26) + 'A';
    }
    decrypted[len] = '\0';
    printf("Decrypted Text: %s\n", decrypted);

    return 0;
}
```

## OUTPUT:
<img width="527" height="286" alt="image" src="https://github.com/user-attachments/assets/167ee2a7-e11a-47c7-b981-cac6833f35a2" />


## RESULT:
  Thus the Vigenere Cipher substitution technique had been implemented successfully.
