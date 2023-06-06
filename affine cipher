#include <iostream>
#include <string>

using namespace std;

int modInverse(int a, int m) {
    a = a % m;
    for (int x = 1; x < m; x++) {
        if ((a * x) % m == 1) {
            return x;
        }
    }
    return -1;
}

string affineEncrypt(string plaintext, int a, int b) {
    string ciphertext = "";
    int n = plaintext.length();

    for (int i = 0; i < n; i++) {
        if (plaintext[i] != ' ') {
            char encryptedChar = (a * (plaintext[i] - 'A') + b) % 26 + 'A';
            ciphertext += encryptedChar;
        } else {
            ciphertext += ' ';
        }
    }

    return ciphertext;
}

string affineDecrypt(string ciphertext, int a, int b) {
    string plaintext = "";
    int n = ciphertext.length();
    int aInverse = modInverse(a, 26);

    for (int i = 0; i < n; i++) {
        if (ciphertext[i] != ' ') {
            char decryptedChar = (aInverse * (ciphertext[i] - 'A' - b + 26)) % 26 + 'A';
            plaintext += decryptedChar;
        } else {
            plaintext += ' ';
        }
    }

    return plaintext;
}

int main() {
    string plaintext;
    int a, b;

    cout << "Enter plaintext: ";
    getline(cin, plaintext);

    cout << "Enter value for 'a': ";
    cin >> a;

    cout << "Enter value for 'b': ";
    cin >> b;

    string encryptedText = affineEncrypt(plaintext, a, b);
    string decryptedText = affineDecrypt(encryptedText, a, b);

    cout << "Encrypted text: " << encryptedText << endl;
    cout << "Decrypted text: " << decryptedText << endl;

    return 0;
}
