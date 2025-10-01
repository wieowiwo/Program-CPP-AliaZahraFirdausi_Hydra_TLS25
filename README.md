# Program-CPP-AliaZahraFirdausi_Hydra_TLS25
#include <iostream>
using namespace std;


int reverseInt(int n) {
    int reversed = 0;
    while (n > 0) {
        reversed = reversed * 10 + (n % 10);
        n /= 10;
    }
    return reversed;
}

int main() {
    string text;
    cout << "Masukkan kata sandi asli: ";
    cin >> text;

    int code[100]; // array untuk menyimpan kode sandi
    int length = text.length();

    cout << "\n=== Enkripsi ===" << endl;
    for (int i = 0; i < length; i++) {
        int ascii = (int)text[i];       // simpan ASCII
        code[i] = reverseInt(ascii);    // balik secara matematis
        cout << code[i] << " ";         // tampilkan kode sandi
    }

    cout << "\n\n=== Dekripsi ===" << endl;
    cout << "Sebagian kata asli: ";
    for (int i = 0; i < length; i++) {
        int originalAscii = reverseInt(code[i]); // balik lagi ke ASCII asli
        char originalChar = (char)originalAscii; // ubah ke karakter
        cout << originalChar;
    }

    cout << endl;
    return 0;
}
