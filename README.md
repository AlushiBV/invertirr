# invertirr
invierte el orden de las lineas


#include <iostream>
#include <fstream>
#include <stdlib.h>
using namespace std;

int main()
{


    ifstream inputFile;
    inputFile.open("lenguaje.txt");

    ofstream outputFile;
    outputFile.open("lenguaje1.txt");

if (inputFile.fail()) {
    cout << "error al tratar de abrir el archivo" << endl;

    return 0;
}
if (outputFile.fail()) {
    cout << "No se pudo abrir el archivo lenguaje1" << endl;
    return 0;

}

int i = 0;
int n = 0;
string line[100];
while (getline(inputFile, line[i])) {//aqui leemos  la linea con getline
    n++;
    i++;
}

for (int j = n-1; j >= 0; j--) {  // se le resta 1 para evitar espacio en blanco
    outputFile << line[j] << " " <<endl;
}


inputFile.close();
outputFile.close();

return 0; 
}
