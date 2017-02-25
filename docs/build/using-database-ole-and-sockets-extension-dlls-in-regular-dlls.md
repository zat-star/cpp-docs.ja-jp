---
title: "レギュラー DLL でのデータベース、OLE、およびソケット拡張 DLL の使用 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DLL [C++], 拡張機能"
  - "DLL [C++], 初期化"
  - "DLL [C++], 標準"
ms.assetid: 9f1d14a7-9e2a-4760-b3b6-db014fcdb7ff
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# レギュラー DLL でのデータベース、OLE、およびソケット拡張 DLL の使用
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

レギュラー DLL から拡張 DLL を使用するときに、拡張 DLL がレギュラー DLL の **CDynLinkLibrary** オブジェクト チェーンにリンクされていない場合、問題が発生することがあります。  MFC データベース OLE、およびソケット サポート DLL のデバッグ バージョンは、拡張 DLL として実装されているので、独自の拡張 DLL を明示的に使用していなくても、これらの MFC 機能を使用する場合に同様の問題が発生することもあります。  問題の徴候は、以下のとおりです。  
  
-   拡張 DLL 内で定義されたクラス型を持つオブジェクトを非シリアル化しようとすると、TRACE デバッグ ウィンドウに "Warning: Cannot load CYourClass from archive.   Class not defined." というメッセージが表示され、オブジェクトの非シリアル化が失敗します。  
  
-   不正なクラスを示す例外がスローされる可能性があります。  
  
-   拡張 DLL 内に格納されたリソースの読み込みが失敗します。これは、`AfxFindResourceHandle` が **NULL** または不正なリソース ハンドルを返すからです。  
  
-   `DllGetClassObject`、`DllCanUnloadNow`、および `COleObjectFactory` のメンバー関数 \(`UpdateRegistry`、`Revoke`、`RevokeAll`、`RegisterAll`\) が、拡張 DLL 内で定義されたクラス ファクトリの配置に失敗します。  
  
-   `AfxDoForAllClasses` が拡張 DLL 内のどのクラスでも動作しません。  
  
-   標準 MFC データベース、ソケット、または OLE リソースの読み込みが失敗します。  たとえば、**AfxLoadString**\(**AFX\_IDP\_SQL\_CONNECT\_FAIL**\) は、レギュラー DLL による MFC データベース クラスの使い方が正しくても、空の文字列を返します。  
  
 これらの問題を解決するには、**CDynLinkLibrary** オブジェクトを作成する初期化関数を拡張 DLL 内に作成し、エクスポートします。  拡張 DLL を使用する各レギュラー DLL から正確に一度ずつ、この初期化関数を呼び出します。  
  
## MFC OLE、MFC データベース \(DAO\)、および MFC ソケットのサポート  
 レギュラー DLL 内の MFC OLE、MFC データベース \(DAO\)、および MFC ソケットのサポートを使用している場合は、MFC デバッグ拡張 DLL である MFCOxxD.dll、MFCDxxD.dll、および MFCNxxD.dll が自動的にリンクされます。xx はバージョン番号を表します。  使用する DLL ごとに、定義済みの初期化関数を呼び出す必要があります。  
  
 データベース サポートを使用する場合は、`AfxDbInitModule` の呼び出しをレギュラー DLL の `CWinApp::InitInstance` 関数に追加します。  この呼び出しは、基本クラスを呼び出す前、または MFCDxxD.dll にアクセスするコードを追加する前に行う必要があります。  この関数はパラメーターを使用せず、void を返します。  
  
 OLE サポートを使用する場合は、`AfxOleInitModule` の呼び出しをレギュラー DLL の `CWinApp::InitInstance` 関数に追加します。  **COleControlModule InitInstance** 関数が、既に `AfxOleInitModule` を呼び出していることに注意してください。OLE コントロールをビルドしていて、`COleControlModule` を使用している場合は、`AfxOleInitModule` の呼び出しを追加しないでください。  
  
 ソケット サポートを使用する場合は、`AfxNetInitModule` の呼び出しをレギュラー DLL の `CWinApp::InitInstance` 関数に追加します。  
  
 MFC DLL およびアプリケーションのリリース ビルドでは、データベース サポート、ソケット サポート、または OLE サポートで個別の DLL を使用しないでください。  ただし、リリース モードでのこれらの初期化関数の呼び出しは安全です。  
  
## CDynLinkLibrary オブジェクト  
 このトピックの冒頭に述べた各操作中、MFC では必要な値またはオブジェクトを検索する必要があります。  たとえば、非シリアル化を行う間、MFC は現時点で使用可能なすべてのランタイム クラスを検索して、アーカイブ内のオブジェクトを正しいランタイム クラスに対応付けます。  
  
 このような検索の一部として、MFC では **CDynLinkLibrary** オブジェクト チェーンを検索して使用中のすべての拡張 DLL をスキャンします。  **CDynLinkLibrary** オブジェクトは、コンストラクターの中で自動的にチェインにアタッチされ、各拡張 DLL によって初期化時に作成されます。  さらに、すべてのモジュール \(アプリケーションまたはレギュラー DLL\) には、独自の **CDynLinkLibrary** オブジェクト チェインがあります。  
  
 拡張 DLL を **CDynLinkLibrary** チェーンにリンクするには、その拡張 DLL を使用する各モジュールのコンテキスト内に **CDynLinkLibrary** オブジェクトを作成する必要があります。  このため、レギュラー DLL から拡張 DLL を使用する予定がある場合は、**CDynLinkLibrary** オブジェクトを作成するエクスポート初期化関数を提供する必要があります。  拡張 DLL を使用する各レギュラー DLL は、そのエクスポート初期化関数を呼び出します。  
  
 拡張 DLL を使用するのが MFC アプリケーション \(.exe\) だけで、レギュラー DLL からは使用しない場合は、その拡張 DLL の `DllMain` 内に **CDynLinkLibrary** オブジェクトを作成するだけで十分です。  この作成は、MFC DLL ウィザード の拡張 DLL コードで行います。  拡張 DLL を暗黙に読み込む場合、`DllMain` はアプリケーションが開始する前に読み込まれ、実行されます。  作成された **CDynLinkLibrary** は、MFC DLL が MFC アプリケーション用に保存する既定のチェインにリンクされます。  
  
 1 つのチェイン内の 1 つの拡張 DLL から複数の **CDynLinkLibrary** オブジェクトを作成することは、お勧めできません。特に、その拡張 DLL がメモリから動的にアンロードされる場合はお勧めできません。  また、1 つのモジュールから初期化関数を 2 度以上呼び出さないでください。  
  
## サンプル コード  
 次のサンプル コードでは、レギュラー DLL が暗黙に拡張 DLL にリンクされていると仮定しています。  これを実現するには、レギュラー DLL のビルド時に、拡張 DLL のインポート ライブラリ \(.lib\) とリンクします。  
  
 以下は、拡張 DLL のソースの内容です。  
  
```  
// YourExtDLL.cpp:  
  
// standard MFC extension DLL routines  
#include "afxdllx.h"  
  
static AFX_EXTENSION_MODULE NEAR extensionDLL = { NULL, NULL };  
  
extern "C" int APIENTRY  
DllMain(HINSTANCE hInstance, DWORD dwReason, LPVOID lpReserved)  
{  
    if (dwReason == DLL_PROCESS_ATTACH)  
    {  
        // extension DLL one-time initialization  
        if (!AfxInitExtensionModule(extensionDLL, hInstance))  
           return 0;  
    }  
    return 1;   // ok  
}  
  
// Exported DLL initialization is run in context of  
// application or regular DLL  
extern "C" void WINAPI InitYourExtDLL()  
{  
    // create a new CDynLinkLibrary for this app  
    new CDynLinkLibrary(extensionDLL);  
  
    // add other initialization here  
}  
```  
  
 **InitYourExtDLL** 関数を必ずエクスポートします。  このためには、**\_\_declspec\(dllexport\)** を使うか、DLL の .def ファイルに以下の行を記述します。  
  
```  
// YourExtDLL.Def:  
LIBRARY      YOUREXTDLL  
CODE         PRELOAD MOVEABLE DISCARDABLE  
DATA         PRELOAD SINGLE  
EXPORTS  
    InitYourExtDLL  
```  
  
 拡張 DLL を使って、各レギュラー DLL 内の `CWinApp` 派生オブジェクトの `InitInstance` メンバーの呼び出しを追加します。  
  
```  
// YourRegularDLL.cpp:  
  
class CYourRegularDLL : public CWinApp  
{  
public:  
    virtual BOOL InitInstance(); // Initialization  
    virtual int ExitInstance();  // Termination  
  
    // nothing special for the constructor  
    CYourRegularDLL(LPCTSTR pszAppName) : CWinApp(pszAppName) { }  
};  
  
BOOL CYourRegularDLL::InitInstance()  
{  
    // any DLL initialization goes here  
    TRACE0("YOUR regular DLL initializing\n");  
  
    // wire any extension DLLs into CDynLinkLibrary chain  
    InitYourExtDLL();  
  
    return TRUE;  
}  
```  
  
### 目的に合ったトピックをクリックしてください  
  
-   [拡張 DLL の初期化](../build/initializing-extension-dlls.md)  
  
-   [レギュラー DLL の初期化](../Topic/Initializing%20Regular%20DLLs.md)  
  
### さらに詳しくは次のトピックをクリックしてください  
  
-   [拡張 DLLs](../build/extension-dlls.md)  
  
-   [MFC と静的にリンクされるレギュラー DLL](../build/regular-dlls-statically-linked-to-mfc.md)  
  
-   [MFC と動的にリンクされるレギュラー DLL](../Topic/Regular%20DLLs%20Dynamically%20Linked%20to%20MFC.md)  
  
-   [DLL の構成要素としての MFC](../mfc/tn011-using-mfc-as-part-of-a-dll.md)  
  
-   [テクニカル ノート 33: MFC の DLL バージョン](../mfc/tn033-dll-version-of-mfc.md)  
  
## 参照  
 [拡張 DLL](../build/extension-dlls.md)