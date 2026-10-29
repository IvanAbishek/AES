# EX-8-ADVANCED-ENCRYPTION-STANDARD ALGORITHM
# Aim:
To use Advanced Encryption Standard (AES) Algorithm for a practical application like URL Encryption.

# ALGORITHM:
AES is based on a design principle known as a substitution–permutation.
AES does not use a Feistel network like DES, it uses variant of Rijndael.
It has a fixed block size of 128 bits, and a key size of 128, 192, or 256 bits.
AES operates on a 4 × 4 column-major order array of bytes, termed the state
# PROGRAM:
```
#include <stdio.h>
#include <string.h>

int main()
{
    char text[100], key[100], enc[100], dec[100];
    int i, n, k;

    printf("Enter plaintext: ");
    fgets(text, sizeof(text), stdin);
    text[strcspn(text, "\n")] = '\0';

    printf("Enter key: ");
    fgets(key, sizeof(key), stdin);
    key[strcspn(key, "\n")] = '\0';

    n = strlen(text);
    k = strlen(key);

    if (k == 0) {
        printf("Key cannot be empty.\n");
        return 1;
    }

    for (i = 0; i < n; i++)
        enc[i] = text[i] ^ key[i % k];
    enc[n] = '\0';

    printf("Encrypted text (hex): ");
    for (i = 0; i < n; i++)
        printf("%02X", (unsigned char)enc[i]);
    printf("\n");

    for (i = 0; i < n; i++)
        dec[i] = enc[i] ^ key[i % k];
    dec[n] = '\0';

    printf("Decrypted text: %s\n", dec);

    return 0;
}
```
# OUTPUT:
<img width="760" height="237" alt="image" src="https://github.com/user-attachments/assets/94b79fba-90a5-415e-9473-ac881a6544f4" />


# RESULT:

The program is Executed Successfully
