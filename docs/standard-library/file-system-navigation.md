---
title: "ファイル システムのナビゲーション | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: f7cc5f5e-a541-4e00-87c7-a3769ef6096d
caps.latest.revision: 14
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# ファイル システムのナビゲーション
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

\<filesystem\> ヘッダーは、ドラフトの File System Technical Specification \([ISO\/IEC JTC 1\/SC 22\/WG 21 N4100](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4100.pdf)\) を実装し、型および関数により、ファイル システムを移動するためのプラットフォームに依存しないコードを記述できます。 それはクロス プラットフォームなので、Windows システムに関連しない API が含まれます。 たとえば、Windows では `is_fifo(const path&)` は常に `false` を返します。 ヘッダーは、Visual Studio 2015 RTM の段階で C\+\+17 標準には認められていないドラフトの技術仕様に基づいています。 そのメンバーは `std::experimental::filesystem::v1` 名前空間にあります。  
  
## 概要  
 \<filesystem\> API を次のタスクに使用します。  
  
-   指定のパスの下のファイルとディレクトリを反復処理します。  
  
-   ファイルの作成時、サイズ、拡張子、およびルート ディレクトリなどに関するファイルの情報を取得します。  
  
-   パスの構成、分解、および比較  
  
-   ディレクトリの作成、コピー、および削除  
  
-   ファイルのコピーと削除  
  
 標準ライブラリを使用したファイル IO の詳細については、「[iostream プログラミング](../Topic/iostream%20Programming.md)」を参照してください。  
  
## パス  
  
### パスの構成および描画  
 \(XP 以降の\) Windows のパスは、ネイティブで Unicode で格納されます。[path](../Topic/path%20Class%20\(C++%20Standard%20Template%20Library\).md) クラスは、自動的にすべての必要な文字列の変換を実行します。 それはワイド文字とナロー文字の両方の配列の引数を受け入れ、UTF8 や UTF16 として書式設定された `std::string` や `std::wstring` 型も受け入れます。`path` クラスは、パスの区切り記号も自動的に正規化します。 コンストラクターの引数のディレクトリの区切り記号として単一のスラッシュを使用することができます。 これにより、Windows と UNIX の両方の環境でのパスの格納に、同じ文字列を使用することができます。  
  
```cpp  
path pathToDisplay(L"/FileSystemTest/SubDir3"); // OK! path pathToDisplay2(L"\\FileSystemTest\\SubDir3"); // Still OK as always path pathToDisplay3(LR"(\FileSystemTest\SubDir3)"); // Raw string literals are OK, too.  
```  
  
 2 つのパスを連結する際、オーバーロードされた  `/` と `/=` 演算子を使用できますが、これは `std::string` および `std::wstring` の`+` と `+=` 演算子と似ています。`path` オブジェクトは、ユーザーが区切り文字を指定していない場合に、便利にそれを指定できます。  
  
```cpp  
path myRoot("C:/FileSystemTest"); // no trailing separator, no problem! myRoot /= path("SubDirRoot"); // C:/FileSystemTest/SubDirRoot  
```  
  
### パスの確認  
 path クラスは、参照するファイル システム エンティティとは異なる、パス自体の様々な部分に関する情報を返すいくつかのメソッドを持っています。 ルート、相対パス、ファイル名、および、ファイル拡張子などを取得できます。 階層内のすべてのフォルダーを確認するために、パス オブジェクトで反復処理することができます。 次の例では \(参照するディレクトリではなく\) パスを繰り返し処理して、そのパーツに関する情報を取得する方法を示します。  
  
```cpp  
  
#include <string> #include <iostream> #include <sstream> #include <filesystem> using namespace std; using namespace std::experimental::filesystem::v1; wstring  DisplayPathInfo() { // This path may or may not refer to an existing file. We are // examining this path string, not file system objects. path pathToDisplay(L"C:/FileSystemTest/SubDir3/SubDirLevel2/File2.txt "); wostringstream wos; int i = 0; wos << L"Displaying path info for: " << pathToDisplay << endl; for (path::iterator itr = pathToDisplay.begin(); itr != pathToDisplay.end(); ++itr) { wos << L"path part: " << i++ << L" = " << *itr << endl; } wos << L"root_name() = " << pathToDisplay.root_name() << endl << L"root_path() = " << pathToDisplay.root_path() << endl << L"relative_path() = " << pathToDisplay.relative_path() << endl << L"parent_path() = " << pathToDisplay.parent_path() << endl << L"filename() = " << pathToDisplay.filename() << endl << L"stem() = " << pathToDisplay.stem() << endl << L"extension() = " << pathToDisplay.extension() << endl; return wos.str(); } void main(int argc, char* argv[]) { wcout << DisplayPathInfo() << endl; // wcout << ComparePaths() << endl; // see following example wcout << endl << L"Press Enter to exit" << endl; wstring input; getline(wcin, input); }  
```  
  
 このコードでは、次の出力が生成されます:  
  
```cpp  
Displaying path info for: C:\FileSystemTest\SubDir3\SubDirLevel2\File2.txt path part: 0 = C: path part: 1 = \ path part: 2 = FileSystemTest path part: 3 = SubDir3 path part: 4 = SubDirLevel2 path part: 5 = File2.txt root_name() = C: root_path() = C:\ relative_path() = FileSystemTest\SubDir3\SubDirLevel2\File2.txt parent_path() = C:\FileSystemTest\SubDir3\SubDirLevel2 filename() = File2.txt stem() = File2 extension() = .txt  
```  
  
### パスの比較  
 `path` クラスは、`std::string` および `std::wstring` と同じ比較演算子をオーバーロードします。 2 つのパスを比較したときに、区切り記号が正規化された後に、文字列の比較を実行します。 末尾のスラッシュ \(または円記号\) が不足している場合は追加されず、比較に影響します。 パスの値を比較する方法を次の例に示します。  
  
```cpp  
  
wstring ComparePaths() { path p0(L"C:/Documents"); // no trailing separator path p1(L"C:/Documents/"); //p0 < p1 path p2(L"C:/Documents/2013/"); // p1 < p2 path p3(L"C:/Documents/2013/Reports/"); // p2 < p3 path p4(L"C:/Documents/2014/");  // p3 < p4 path p5(L"D:/Documents/2013/Reports/"); // p4 < p5 wostringstream wos; wos << boolalpha << p0.wstring() << L" < " << p1.wstring() << L": " << (p0 < p1) << endl << p1.wstring() << L" < " << p2.wstring() << L": " << (p1 < p2) << endl << p2.wstring() << L" < " << p3.wstring() << L": " << (p2 < p3) << endl << p3.wstring() << L" < " << p4.wstring() << L": " << (p3 < p4) << endl << p4.wstring() << L" < " << p5.wstring() << L": " << (p4 < p5) << endl; return wos.str(); } /* Output: C:\Documents < C:\Documents\: true C:\Documents\ < C:\Documents\2013\: true C:\Documents\2013\ < C:\Documents\2013\Reports\: true C:\Documents\2013\Reports\ < C:\Documents\2014\: true C:\Documents\2014\ < D:\Documents\2013\Reports\: true */  
```  
  
 このコードを実行するには、上記の完全なサンプル コードに貼り付けて、main でこれを呼び出す行をコメント解除します。  
  
### パスと文字列型の間の変換  
 `path` オブジェクトは `std::wstring` または `std::string` に暗黙的に変換できます。 つまり、次の例に示すように、[wofstream::open](../Topic/basic_ofstream::open.md) などの関数にパスを渡すことができます。  
  
```cpp  
wchar_t* p = L"C:/test"; path filePath(p); filePath /= L"NewFile.txt"; // Open, write to, and close the file. wofstream myFile; myFile.open(filePath); myFile << L"Lorem ipsum..."; myFile.close  
  
```  
  
## ディレクトリとファイルを反復する  
 \<filesystem\> ヘッダーは、[directory\_iterator](../Topic/directory_iterator%20Class.md) 型を提供して、1 つのディレクトリを反復し、[recursive\_directory\_iterator](../Topic/recursive_directory_iterator%20Class.md) クラスはディレクトリとサブディレクトリを再帰的に反復します。`path` オブジェクトを渡して反復子を構成した後、反復子はパス内の最初の directory\_entry を指します。 既定のコンストラクターを呼び出すことで、終了反復子を作成します。  
  
 ディレクトリを反復しているときに遭遇する可能性がある項目は、ディレクトリ、ファイル、シンボリック リンク、ソケット ファイルなどですが、これらに限定されません。`directory_iterator` は、項目を [directory\_entry](../standard-library/directory-entry-class.md) オブジェクトとして返し、各オブジェクトは探している項目の種類を通知する [status\(\)](http://msdn.microsoft.com/ja-jp/a70a3c55-3a76-417f-abaf-862ff94b2056) メンバーを持っています。 この値を調べることで、特定のエントリの対処方法に関する意思決定をすることができます。 次の例は、1 つのディレクトリを反復処理し、ディレクトリのエントリが通常のファイルの場合に、コードがそのファイルに関する情報を印刷します。 エントリがディレクトリの場合は、名前だけが表示されます。  
  
```cpp  
#include <string> #include <iostream> #include <iomanip> #include <filesystem> #include <chrono> #include <time.h> using namespace std; using namespace std::experimental::filesystem::v1; // Display the last write time for the file wstring LastWriteTimeToLocalTime(const path& file_path) { const auto last = chrono::system_clock::to_time_t(last_write_time(file_path)); tm timeinfo; localtime_s(&timeinfo, &last); wchar_t buf[56]; _wasctime_s(buf, 56, &timeinfo); // appends '\n' return wstring{ buf }; } // List files and directories in the specified path void DisplayFolderContents(const path& p) { wcout << L"Begin iterating " << p.wstring() << endl; for (const auto& entry : directory_iterator{ p }) { if (is_regular_file(entry.status())) { wcout << L" File: " << entry.path().filename() << " : " << LastWriteTimeToLocalTime(entry.path()); } else if (is_directory(entry.status())) { wcout << L" Dir: " << entry.path().filename() << endl; } } } void main() { wstring dir{ LR"(C:\users\public\documents\)" }; path p{ dir }; if (!is_directory(p)) { wcout << L"No such directory: " << dir << endl; return; } DisplayFolderContents(p); // IterateFolderRecursively(p); // see example wcout << endl << L"Press Enter to exit" << endl; wstring input; getline(wcin, input); }  
```  
  
### ディレクトリ ツリーを再帰的に反復処理する  
 次の例では、ディレクトリ ツリーを再帰的に反復処理する方法を示します。 この関数を実行するには、上記のサンプル コードの DisplayFolderContents 関数の後に貼り付け、main でそれを呼び出す行をコメント解除します。  
  
```cpp  
// List files and directories recursively in the path void IterateFolderRecursively(const path& p) { wcout << L"Begin iterating " << p.wstring() << " recursively" << endl; for (recursive_directory_iterator it{ p }, end; it != end; ++it) { if (is_regular_file(it->status())) { wcout << setw(it.depth()) << L" " << L"File: " << it->path().filename() << L" : " << LastWriteTimeToLocalTime(it->path()); } else if (is_directory(it->status())) { wcout << setw(it.depth()) << L" " << L"Dir: " << it->path().filename() << endl; } } }  
```  
  
### シンボリック リンクを処理する  
 シンボリック リンクの検出は、まだ Visual Studio 2015 のVisual C\+\+ ではサポートされません。