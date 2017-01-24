---
title: "拡張 DLL の初期化 | Microsoft Docs"
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
helpviewer_keywords: 
  - "DLL [C++], 拡張機能"
  - "拡張 DLL [C++], 初期化"
  - "初期化 (DLL を)"
ms.assetid: 08ad0381-3808-4bea-a93c-c9ba62496543
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 拡張 DLL の初期化
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

拡張 DLL には、`CWinApp` 派生オブジェクトがないため、MFC DLL ウィザード が生成する `DllMain` 関数に対する初期化コードと終了コードを追加する必要があります。  
  
 ウィザードは、拡張 DLL 用に次のコードを提供します。  次のコードにある `PROJNAME` は、プロジェクト名のプレースホルダーです。  
  
```  
#include "stdafx.h"  
#include <afxdllx.h>  
  
#ifdef _DEBUG  
#define new DEBUG_NEW  
#undef THIS_FILE  
static char THIS_FILE[] = __FILE__;  
#endif  
static AFX_EXTENSION_MODULE PROJNAMEDLL = { NULL, NULL };  
  
extern "C" int APIENTRY  
DllMain(HINSTANCE hInstance, DWORD dwReason, LPVOID lpReserved)  
{  
   if (dwReason == DLL_PROCESS_ATTACH)  
   {  
      TRACE0("PROJNAME.DLL Initializing!\n");  
  
      // Extension DLL one-time initialization  
      AfxInitExtensionModule(PROJNAMEDLL,   
                                 hInstance);  
  
      // Insert this DLL into the resource chain  
      new CDynLinkLibrary(Dll3DLL);  
   }  
   else if (dwReason == DLL_PROCESS_DETACH)  
   {  
      TRACE0("PROJNAME.DLL Terminating!\n");  
   }  
   return 1;   // ok  
}  
```  
  
 初期化時に新しい **CDynLinkLibrary** オブジェクトを作成することによって、拡張 DLL は `CRuntimeClass` オブジェクトやリソースをクライアント アプリケーションにエクスポートできます。  
  
 拡張 DLL を 1 つ以上のレギュラー DLL から使う予定がある場合、**CDynLinkLibrary** オブジェクトを作成する初期化関数をエクスポートする必要があります。  初期化関数の呼び出しは、拡張 DLL を使う各レギュラー DLL から行います。  初期化関数の呼び出しに適した場所は、拡張 DLL のエクスポート クラスまたはエクスポート関数を使う前の、レギュラー DLL の `CWinApp` 派生オブジェクトの `InitInstance` メンバー関数の中です。  
  
 MFC DLL ウィザード が生成する `DllMain` では、**CDynLinkLibrary** が作成されたときのために、`AfxInitExtensionModule` を呼び出すと、オブジェクト ファクトリ \(`COleObjectFactory` オブジェクト\) とモジュールのランタイム クラス \(`CRuntimeClass` 構造体\) がキャプチャされます。  また、`AfxInitExtensionModule` の戻り値を調べる必要があります。`AfxInitExtensionModule` から値 0 が返されると、`DllMain` 関数から 0 を返します。  
  
 拡張 DLL が実行形式と明示的にリンクされる場合 \(つまり、実行形式が `AfxLoadLibrary` を呼び出して DLL にリンクする場合\)、**DLL\_PROCESS\_DETACH** には `AfxTermExtensionModule` の呼び出しを追加する必要があります。  MFC はこの関数を使って、各プロセスが拡張 DLL からデタッチするときに、拡張 DLL をクリアします。プロセスのデタッチは、`AfxFreeLibrary` によって DLL がアンロードされるときか、プロセスが終了するときに発生します。  拡張 DLL がアプリケーションと暗黙的にリンクされる場合、`AfxTermExtensionModule` への呼び出しは不要です。  
  
 DLL と明示的にリンクするアプリケーションは、DLL を解放する時点で **AfxTermExtensionModule**  を呼び出す必要があります。  また、これらのアプリケーションが複数のスレッドを使う場合は、Win32 関数の **LoadLibrary** と **FreeLibrary** ではなく、`AfxLoadLibrary` と `AfxFreeLibrary` を使います。  `AfxLoadLibrary` と `AfxFreeLibrary` を使用することによって、拡張 DLL の読み込みまたはアンロード時に実行されるスタートアップ コードと終了コードが、グローバルな MFC の状態を破損するのを防ぎます。  
  
 16 ビット版の MFC とは異なり、`DllMain` が呼び出される時点までに MFCx0.dll は完全に初期化されているので、`DllMain` でメモリの割り当てや MFC 関数の呼び出しを行うことができます。  
  
 拡張 DLL は、`DllMain` 関数内で **DLL\_THREAD\_ATTACH** と **DLL\_THREAD\_DETACH** の分岐を処理することによって、マルチスレッドを扱うことができます。  これらの分岐は、スレッドと DLL のアタッチ\/デタッチ時に `DllMain` に渡されます。  DLL のアタッチ時に [TlsAlloc](http://msdn.microsoft.com/library/windows/desktop/ms686801) を呼び出すことによって、DLL は、アタッチされる各スレッドの TLS \(スレッド ローカル ストレージ\) インデックスを管理します。  
  
 ヘッダー ファイル Afxdllx.h には、`AFX_EXTENSION_MODULE` や **CDynLinkLibrary** などの拡張 DLL で使われる構造体の特別な定義が含まれています。  このヘッダー ファイルを拡張 DLL にインクルードする必要があります。  
  
> [!NOTE]
>  Stdafx.h 内の \_AFX\_NO\_XXX マクロについては、定義\/定義解除を行わないことが重要です。  詳細については、サポート技術情報の「PRB: Problems Occur When Defining \_AFX\_NO\_XXX \(Q140751\)」を参照してください。  MSDN ライブラリのサポート技術情報の文書"または"を参照してください。[http:\/\/search.support.microsoft.com\/](http://search.support.microsoft.com/)  
  
 マルチスレッドを処理する初期化関数のサンプルは、[!INCLUDE[winsdkshort](../atl/reference/includes/winsdkshort_md.md)] の「[Using Thread Local Storage in a Dynamic\-Link Library](http://msdn.microsoft.com/library/windows/desktop/ms686997)」に含まれています。  このサンプルでは、**LibMain** というエントリ ポイント関数が使われていますが、MFC および C ランタイム ライブラリで実行するためには、この関数を `DllMain` と置き換える必要があります。  
  
 MFC のサンプル [DLLHUSK](http://msdn.microsoft.com/ja-jp/dfcaa6ff-b8e2-4efd-8100-ee3650071f90) では、初期化関数の使い方が説明されています。  
  
## 目的に合ったトピックをクリックしてください  
  
-   [レギュラー DLL の初期化](../Topic/Initializing%20Regular%20DLLs.md)  
  
-   [非 MFC DLL の初期化](../Topic/Initializing%20Non-MFC%20DLLs.md)  
  
## さらに詳しくは次のトピックをクリックしてください  
  
-   [C ランタイム ライブラリの動作と \_DllMainCRTStartup](../build/run-time-library-behavior.md)  
  
-   [レギュラー DLL でのデータベース、OLE、およびソケット拡張 DLL の使用](../build/using-database-ole-and-sockets-extension-dlls-in-regular-dlls.md)  
  
-   [\<caps:sentence id\="tgt34" sentenceid\="58bb7328659bda9ffb73a1dcd39da06b" class\="tgtSentence"\>The function specification for DllMain \(Windows SDK\)\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/ms682583)  
  
-   [\<caps:sentence id\="tgt35" sentenceid\="f29344705c59343b34b642944921cbdf" class\="tgtSentence"\>Dynamic\-link library entry\-point function \(Windows SDK\)\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/ms682596)  
  
## 参照  
 [DLL の初期化](../build/initializing-a-dll.md)