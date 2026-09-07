# NAME: mohamedasil s
## REG NO:212223040112
## DATE:24.07.2026 
# VIGENERE-CIPHER
## EX. NO: 4
 

## IMPLEMETATION OF VIGENERE CIPHER
 

## AIM:

To implement the Vigenere Cipher substitution technique using C program.

## DESCRIPTION:

To encrypt, a table of alphabets can be used, termed a tabula recta, Vigenère square,or Vigenère table. It consists of the alphabet written out 26 times in differnt rows, each
 
alphabet shifted cyclically to the left compared to the previous alphabet, corresponding to the 26 possible Caesar ciphers. At different points in the encryption process, the cipher uses adifferent alphabet from one of the rows. The alphabet used at each point repeating keyword.depends on a Each row starts with a key letter. The remainder of the row holds the letters A to Z. Although there are 26 key rows shown, you will only use as many keys as there are unique letters in the key string, here just 5 keys, {L, E, M, O, N}. For successive letters of the message, we are going to take successive letters of the key string, and encipher each message letter using its corresponding key row. Choose the next letter of the key, go along that row to find the column heading that	atches the message character; the letter at the intersection of
[key-row, msg-col] is the enciphered letter.


## ALGORITHM:

STEP-1: Arrange the alphabets in row and column of a 26*26 matrix.
STEP-2: Circulate the alphabets in each row to position left such that the first letter is attached to last.
STEP-3: Repeat this process for all 26 rows and construct the final key matrix.
STEP-4: The keyword and the plain text is read from the user.
STEP-5: The characters in the keyword are repeated sequentially so as to match with that of the plain text.
STEP-6: Pick the first letter of the plain text and that of the keyword as the row indices and column indices respectively.
STEP-7: The junction character where these two meet forms the cipher character.
STEP-8: Repeat the above steps to generate the entire cipher text.


## PROGRAM
```
#include <stdio.h>
#include <string.h>

void encrypt(char text[], char key[])
{
    int i, k = strlen(key);

    for (i = 0; text[i] != '\0'; i++)
    {
        if (text[i] >= 'A' && text[i] <= 'Z')
            text[i] = ((text[i] - 'A' + key[i % k] - 'A') % 26) + 'A';
        else if (text[i] >= 'a' && text[i] <= 'z')
            text[i] = ((text[i] - 'a' + key[i % k] - 'A') % 26) + 'a';
    }
}

void decrypt(char text[], char key[])
{
    int i, k = strlen(key);

    for (i = 0; text[i] != '\0'; i++)
    {
        if (text[i] >= 'A' && text[i] <= 'Z')
            text[i] = ((text[i] - 'A' - (key[i % k] - 'A') + 26) % 26) + 'A';
        else if (text[i] >= 'a' && text[i] <= 'z')
            text[i] = ((text[i] - 'a' - (key[i % k] - 'A') + 26) % 26) + 'a';
    }
}

int main()
{
    char text[100], key[100];

    printf("Enter Message: ");
    scanf("%s", text);

    printf("Enter Key: ");
    scanf("%s", key);

    encrypt(text, key);
    printf("Encrypted Message: %s\n", text);

    decrypt(text, key);
    printf("Decrypted Message: %s\n", text);

    return 0;
}
```

## OUTPUT
<img width="1398" height="868" alt="image" src="https://github.com/user-attachments/assets/a6e70c5b-bbab-427b-ab49-795c1a98ee1b" />


## RESULT:
Thus the program executed successfully



