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

Compares two character strings, for a locale specified by identifier.

````c++
int CompareStringW(
  LCID                              Locale,
  DWORD                             dwCmpFlags,
  _In_NLS_string_(cchCount1)PCNZWCH lpString1,
  int                               cchCount1,
  _In_NLS_string_(cchCount2)PCNZWCH lpString2,
  int                               cchCount2
);
````

Locale

Locale identifier of the locale used for the comparison.

- LOCALE_CUSTOM_DEFAULT
- LOCALE_CUSTOM_UI_DEFAULT
- LOCALE_CUSTOM_UNSPECIFIED
- LOCALE_INVARIANT
- LOCALE_SYSTEM_DEFAULT
- LOCALE_USER_DEFAULT

dwCmpFlags

Flags that indicate how the function compares the two strings. 

lpString1

Pointer to the first string to compare.

cchCount1

Length of the string indicated by *lpString1*, excluding the terminating null character. This value represents bytes for the ANSI version of the function and wide characters for the Unicode version. The application can supply a negative value if the string is null-terminated. In this case, the function determines the length automatically.

lpString2

Pointer to the second string to compare.

cchCount2

Length of the string indicated by *lpString2*, excluding the terminating null character. This value represents bytes for the ANSI version of the function and wide characters for the Unicode version. The application can supply a negative value if the string is null-terminated. In this case, the function determines the length automatically.

#### CompareStringOrdinal

Compara dos string de unicode para probar la equivalencia en binario.

````c++
int CompareStringOrdinal(
  _In_NLS_string_(cchCount1)LPCWCH lpString1,
  int                              cchCount1,
  _In_NLS_string_(cchCount2)LPCWCH lpString2,
  int                              cchCount2,
  BOOL                             bIgnoreCase
);

// lpString1
// Puntero al primer string a comparar

// cchCount1
// El tamano del string del lpString1, La aplicación proporciona -1 si la cadena tiene terminación nula. En este caso, la función determina la longitud automáticamente.

// lpString2
// Puntero al segundo string a comparar

// cchCount2
// Longitud de la cadena indicada por lpString2. La aplicación proporciona -1 si la cadena tiene terminación nula. En este caso, la función determina la longitud automáticamente.

// bIgnoreCase
// TRUE si la función es realizar una comparación insensible a mayúsculas / minúsculas, utilizando la información de la tabla en mayúsculas del sistema operativo. La aplicación establece este parámetro en FALSE si la función es comparar las cadenas exactamente como se pasan.
````

RETURN VALUE

Devuelve uno de los siguientes valores si tiene éxito. Para mantener la convención de tiempo de ejecución de C de comparar cadenas, el valor 2 se puede sustraer de un valor de retorno distinto de cero. Entonces, el significado de <0, == 0 y> 0 es consistente con el tiempo de ejecución de C.

- CSTR_LESS_THAN. The value indicated by *lpString1* is less than the value indicated by *lpString2*.
- CSTR_EQUAL. The value indicated by *lpString1* equals the value indicated by *lpString2*.
- CSTR_GREATER_THAN. The value indicated by *lpString1* is greater than the value indicated by *lpString2*.

La función devuelve 0 si no tiene éxito. Para obtener información de error extendida, la aplicación puede llamar a GetLastError, que puede devolver uno de los siguientes códigos de error:

- ERROR_INVALID_PARAMETER. Any of the parameter values was invalid.

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

Asigna una cadena UTF-16 (carácter ancho) a una nueva cadena de caracteres. La nueva cadena de caracteres no es necesariamente de un juego de caracteres multibyte.

````c++
int WideCharToMultiByte(
  UINT                               CodePage,
  DWORD                              dwFlags,
  _In_NLS_string_(cchWideChar)LPCWCH lpWideCharStr,
  int                                cchWideChar,
  LPSTR                              lpMultiByteStr,
  int                                cbMultiByte,
  LPCCH                              lpDefaultChar,
  LPBOOL                             lpUsedDefaultChar
);
````

CodePage

Code page to use in performing the conversion. This parameter can be set to the value of any code page that is installed or available in the operating system. 

dwFlags

Flags indicating the conversion type. The application can specify a combination of the following values. The function performs more quickly when none of these flags is set. The application should specify WC_NO_BEST_FIT_CHARS and WC_COMPOSITECHECK with the specific value WC_DEFAULTCHAR to retrieve all possible conversion results. If all three values are not provided, some results will be missing.

For the code pages listed below, *dwFlags* must be 0. Otherwise, the function fails with ERROR_INVALID_FLAGS.

- 50220
- 50221
- 50222
- 50225
- 50227
- 50229
- 57002 through 57011
- 65000 (UTF-7)
- 42 (Symbol)

lpWideCharStr

Pointer to the Unicode string to convert.

cchWideChar

Size, in characters, of the string indicated by *lpWideCharStr*. Alternatively, this parameter can be set to -1 if the string is null-terminated. If *cchWideChar* is set to 0, the function fails.

If this parameter is -1, the function processes the entire input string, including the terminating null character. Therefore, the resulting character string has a terminating null character, and the length returned by the function includes this character.

If this parameter is set to a positive integer, the function processes exactly the specified number of characters. If the provided size does not include a terminating null character, the resulting character string is not null-terminated, and the returned length does not include this character.

lpMultiByteStr

Pointer to a buffer that receives the converted string.

cbMultiByte

Size, in bytes, of the buffer indicated by *lpMultiByteStr*. If this parameter is set to 0, the function returns the required buffer size for *lpMultiByteStr* and makes no use of the output parameter itself.

lpDefaultChar

Pointer to the character to use if a character cannot be represented in the specified code page. The application sets this parameter to **NULL** if the function is to use a system default value.

For the CP_UTF7 and CP_UTF8 settings for *CodePage*, this parameter must be set to **NULL**. Otherwise, the function fails with ERROR_INVALID_PARAMETER.

lpUsedDefaultChar

Pointer to a flag that indicates if the function has used a default character in the conversion. The flag is set to **TRUE** if one or more characters in the source string cannot be represented in the specified code page. Otherwise, the flag is set to **FALSE**. This parameter can be set to **NULL**.

For the CP_UTF7 and CP_UTF8 settings for *CodePage*, this parameter must be set to **NULL**. Otherwise, the function fails with ERROR_INVALID_PARAMETER.

Return Value

If successful, returns the number of bytes written to the buffer pointed to by *lpMultiByteStr*. If the function succeeds and *cbMultiByte* is 0, the return value is the required size, in bytes, for the buffer indicated by *lpMultiByteStr*. Also see *dwFlags* for info about how the WC_ERR_INVALID_CHARS flag affects the return value when invalid sequences are input.

La función devuelve 0 si no tiene éxito. Para obtener información de error extendida, la aplicación puede llamar a GetLastError, que puede devolver uno de los siguientes códigos de error:

- ERROR_INSUFFICIENT_BUFFER. A supplied buffer size was not large enough, or it was incorrectly set to **NULL**.
- ERROR_INVALID_FLAGS. The values supplied for flags were not valid.
- ERROR_INVALID_PARAMETER. Any of the parameter values was invalid.
- ERROR_NO_UNICODE_TRANSLATION. Invalid Unicode was found in a string.

https://docs.microsoft.com/en-us/windows/desktop/api/stringapiset/nf-stringapiset-widechartomultibyte

## Clase 3

### .OBJ

http://www.opengl-tutorial.org/es/beginners-tutorials/tutorial-7-model-loading/

### .X

Code for reading a .tga document type, create CTextureManager

CApp:

- Window
- Renderer
- Texture manager

### .FBX

Este guarda mas informacion de la escena, no solo la iluminacion, esta guarda datos de la escena. No se tienen que contar los vertices.

````c++
// Indices a los vertices
PolygonVertexIndex; // Los indices negativos es cuando se termina el triangulo

Layer                                                                                  

````

### Design Patterns

- Creational Patterns: Abstract Factory, Builder, Factory Method, Prototype, Singleton.
- Structural Patterns: Adapter, Bridge,Composite, Decoration, Flyweight, Proxy.
- Behavioral Patterns: Command, Interpreter, Iterator, Mediator, Observer, State, Strategy, Visitor.

### Trees

A tree is a struct of data, the main characteristic is that the information is save on nodes that save the information, and get new branches from those nodes.

Ways of tracking:

- Pre - Order: Root, Left, Right.
- In - Order: Left, Root, Right. (The numbers are in order)
- Post - Order: Left, right, root.

## Clase 4

#### Factory Method

We pass the different object that returns a new value on a switch, this pattern doesn't have sub classes, is more information but it depends on the implementation. This methods are static, so we don't need to create an object of the class, instead we initialize the object:

````c++
widgetFactory::CreateWindow(0);
````

#### Singleton

Is used when we use only one instance to all the system.

````c++
// ============================== .h
class Logger
{
    public:
    static Logger *getInstance(); // Return a pointer to the class
    void Log(std::string x); // get an instance of the class
    private:
    static Logger * m_instance;	// Need to be initialize on .cpp global	
    Logger();
}
// ============================== .cpp
Logger* Logger::m_instance = null;
Logger * Logger::getInstance()
{	// Check if the instance is null
    if(m_instance == nullptr)
    {	// Create the instance
        m_instance == new Logger();
    } // else, return the instance
    return m_instance;
}

// ============================== Is correct
Logger * log Logger::getInstance(); // Correct
Logger * log2 = new Logger(); // The constructor is private
Logger log3; // Is not pointer
````



## Homework

### Builder

### Prototype

## Grid

````c++
// GridGame
gridGame:public CApp
{
private: 
	Grid * m_pGrid; // Este representa el grid completo
	vector <CGameobject*> m_pGameObjects;// Lista master de objetos
	vector <3DObject*> m_pMeshes;
	initialize(); //  m_inGrid = new Grid(...)
}

// CGameObject
CGameObject
{
	C3Dobject * m_pMesh;
	float m_scale;
}


// CGrid
CGrid
{
private:
    GridCell * m_pGridCell; // Este apuntador, apunta a todas las celdad
    int m_size; // 3
    int m_cellsize;
    void buildWorld(); // Coordenadas de nuestros objetos
    void Load3DObjects(); // Cargar diferentes modelos de meshes
    // Para cada celda calcular los 6 vertices 
	// en este for de define el tipo de grid, pointy o flat
}

// GridCell - Representa cada celda
CGridCell
{
	CGameobject *m_pGameobject; // Se enlaza con m_gameObjects
	CVector3D m_pVertices[6]; // En base a estos vertices , realizar triangulos para render.
	CVector3D m_CenterPoint;
	int x, y , z; // No se esta seguro si sera necesario para calcular la coordenada
}


````

## Threads and Process

````c++
BOOL CreateProcessA(
  LPCSTR                lpApplicationName,     	 // Direccion completa de ejecutable
  LPSTR                 lpCommandLine,			// Linea de comandos o NULL
  LPSECURITY_ATTRIBUTES lpProcessAttributes,  	 // Definir si Kernel objects se pueden hederar
  LPSECURITY_ATTRIBUTES lpThreadAttributes,		 // NULL
  BOOL                  bInheritHandles,     	 // False
  DWORD                 dwCreationFlags,		 // 0 
  LPVOID                lpEnvironment, 			 // omitir
  LPCSTR                lpCurrentDirectory,		 // omitir
  LPSTARTUPINFOA        lpStartupInfo,			 // omitir
  LPPROCESS_INFORMATION lpProcessInformation	 // Se crea variable y se le pasa
);
````

````c++
HANDLE CreateThread(
  LPSECURITY_ATTRIBUTES   lpThreadAttributes, 		// NULL
  SIZE_T                  dwStackSize,			    // 0 - tamano del stack
  LPTHREAD_START_ROUTINE  lpStartAddress,			// Nombre de la funcion para ejecutar en el thread, DWORD WINAPI MyThreadFunc(LPVOID param); esto es para que windows lo reconozca 
  __drv_aliasesMem LPVOID lpParameter,				// Parametro para el thread LPVOID -  Es asi porque se tiene que castear 
  DWORD                   dwCreationFlags,			// 0
  LPDWORD                 lpThreadId				// Se crea variable DWORD threadID y se pasa la referencia &threadID. Es un identificador que le da windows al thread
);
/* Cuando se crea un hilo a los K.O. Se le pueden asignar parametros de seguridad para poder revisar lo que se esta modificando, en este caso no se utilizara*/
````

