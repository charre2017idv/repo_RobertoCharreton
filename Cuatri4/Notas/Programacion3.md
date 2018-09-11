# Programacion 3

Reglas de la clase:

- Evitar uso de celular
- DirectX
- OpenGL
- Libreria para uso de ventanas  de OpenGL = "GLFW"

### Estructura de uso de clases

Se tiene una clase base y de ahi derivan las demas clases que van a trabajar.

Usualmente el destructor virtual debe de estar en la clase base.

Variables de ambiente: Le ayudan a Windows a encontrar ciertas cosas.

Remover

- C3DModel_STLASCII
- CAppHexGrid
- CHexGrid
- CHexGridCell
- CHexWorld

Definir un objeto

Para definir un objeto se requiere:

- Un arreglo dinamico en vertices
- Un arreglo de indices
- Un arreglo de normales
- Un arreglo a las coordenadas de textura

Shaders

Son pequeños programas que se utilizan para ejectuar algo en el programa

## Clase 2 

 DBCS - Double Byte Character Set

Cuando un caracter se pasaba de 250 se tomaba un segundo byte

Unicode 

UTF-8: 1 Byte

UTF-16: 2 Bytes

UTF-32: 4 Bytes

````c++
CreateWindowExA(char *); // Ascii
CreateWindowExW(w_char *); // wide char
// Si existen dos funciones de windows una que acepte ascii y otra wide char, es mejor usar wide char, porque si no esta realiza procesamiento extra.

char a = 'a';
wchar_t b = L'a'; // Es necesario agregar una 'L' para que se identifique como wide char

/* Ascii */
typedef char CHAR;
typedef wchar_t WCHAR;
typedef CHAR* PCHAR;
typedef CHAR* PSTR;
typedef const CHAR* PCSTR;
/* Wide Char */
typedef WCHAR* PWCHAR;
typedef WCHAR* PWSTR;
typedef const WCHAR* PCWSTR;
typedef const WCHAR* LPCWSTR;

/* Definicion de tipos de datos */
// Depende si esta definido en UNICODE o no, sera si los utiliza
#ifdef UNICODE
typedef WCHAr TCHAR, *PTCHAR, *PTSTR;
typedef const WCHAR *PCTSTR;
#else
typedef CHAR TCHAR, *PTCHAR, *PTSTR;
typedef const CHAR *PCTSTR;
#endif

// Ejemplo
# ifdef WIN32
// Codigo que compila en windows
# else
// Codigo que compila en linux
#endif

/* Define - por que es util? */

#define 
````

### Tarea

Cuando la funcion tiene:

Cch = Count of caracters. (numero de caracteres)

Cb = Count of bytes. (Numero de bytes)

#### String CchCat

#### String CchCatEx

#### String CchCopy

#### String CchCopyEx

#### String CchPrintf

#### String CchPrintfEx

#### CompareString

#### CompareStringOrdinal

#### MultiBytetoWideChar

````c++
int MultibytetoWideChar(
    			   UINT uCodePage, 		// Cada lenguaje tiene un codePage interno (Este puede cambiar dependiendo el lenguaje)
                   	WDORD dvFlags, 		// Le dice que hacer en caso de que no se pueda convertir esa cadena a wide char
                   	PCSTR pMultibyteStr, // Puntero constante a la  variable
                   	int cbMultibyte,     // Cantidad de bytes que soporta la variable (strlen(x) * sizeof(char))
                   	PWSTR pWideCharStr,  // Puntero a la variable
                   	int CcharWideChar    // Caracteres maximos que se puede soportar (Se le tiene que pasar una varible wchar para que se guarde el resultado de esa funcion, para saber el tamano de bytes se tiene que convertir)
                   	);
````

#### WideChartoMuliByte

