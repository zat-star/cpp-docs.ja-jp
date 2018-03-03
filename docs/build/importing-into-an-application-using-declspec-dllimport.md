---
title: "_Declspec (dllimport) を使用してアプリケーションへのインポート |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- __declspec
- dllimport
dev_langs:
- C++
helpviewer_keywords:
- __declspec(dllimport) keyword [C++]
- importing DLLs [C++], __declspec(dllimport)
ms.assetid: edb4da4e-f83a-44cf-a668-9239d49dbe42
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9766c6088e3f99711b936b10db0443da49b52c6c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="importing-into-an-application-using-declspecdllimport"></a>__declspec(dllimport) を使ったアプリケーションへのインポート
あるプログラムが DLL によって定義されたパブリック シンボルを使うことを、シンボルをインポートすると言います。 ヘッダー ファイルを作成する場合でビルドする Dll を使用するアプリケーション使用の**_declspec**パブリック シンボルの宣言にします。 キーワード**_declspec**や .def ファイルをエクスポートするかどうかの動作、**方式**キーワード。  
  
 コードを読みやすくするためのマクロを定義**_declspec (dllimport)**し、マクロを使用して、各インポート シンボルを宣言します。  
  
```  
#define DllImport   __declspec( dllimport )  
  
DllImport int  j;  
DllImport void func();  
```  
  
 使用して**_declspec (dllimport)**は関数宣言で省略可能ですが、このキーワードを使用する場合、コンパイラがより効率的なコードを生成します。 ただし、使用する必要があります**_declspec**インポートする実行可能ファイル、DLL のパブリック データ シンボルとオブジェクトにアクセスするためです。 DLL を使う場合は、引き続きインポート ライブラリとリンクする必要があることに注意してください。  
  
 DLL とクライアント アプリケーションには、同じヘッダー ファイルを使うことができます。 こうする場合は、DLL のビルドとクライアント アプリケーションのビルドの区別を示すために、専用のプリプロセッサ シンボルを使います。 例:  
  
```  
#ifdef _EXPORTING  
   #define CLASS_DECLSPEC    __declspec(dllexport)  
#else  
   #define CLASS_DECLSPEC    __declspec(dllimport)  
#endif  
  
class CLASS_DECLSPEC CExampleA : public CObject  
{ ... class definition ... };  
```  
  
## <a name="what-do-you-want-to-do"></a>実行する操作  
  
-   [DLL を初期化します。](../build/run-time-library-behavior.md#initializing-a-dll)  
  
## <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください  
  
-   [インポートして、インライン関数をエクスポートします。](../build/importing-and-exporting-inline-functions.md)  
  
-   [相互インポート](../build/mutual-imports.md)  
  
## <a name="see-also"></a>参照  
 [アプリケーションへのインポート](../build/importing-into-an-application.md)