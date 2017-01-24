---
title: "CStringT を使用した文字列クラスのエクスポート | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CStringT クラス, エクスポート (文字列を)"
ms.assetid: bdfc441e-8d2a-461c-9885-46178066c09f
caps.latest.revision: 15
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CStringT を使用した文字列クラスのエクスポート
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

これまで、MFC の開発者は `CString` から独自の文字列クラスを特化するために書き込みます。  Microsoft Visual C\+\+ .NET 8.0 \(MFC\) では、[CString](../atl-mfc-shared/using-cstring.md) のクラスは [CStringT](../atl-mfc-shared/reference/cstringt-class.md)というテンプレート クラスに置き換えられました。  これは、いくつかの利点を提供しました:  
  
-   このサンプルは、MFC の `CString` のクラスにより、MFC のスタティック リンク ライブラリまたは DLL での ATL プロジェクトで使用されるようにします。  
  
-   新しい `CStringT` テンプレート クラスを使用すると、文字特性を指定する標準テンプレート ライブラリ \(STL\) のテンプレートに似たテンプレート パラメーターを使用して `CString` の動作をカスタマイズできます。  
  
-   `CStringT`を使用して DLL から独自の文字列クラスをエクスポートする場合、コンパイラは、自動的に `CString` の基本クラスをエクスポートします。  `CString` 自体がテンプレート クラスであるため、`CString` は、DLL からインポートするコンパイラを除いて使用すると、コンパイラによってインスタンス化される場合があります。  Visual C\+\+ 6.0 を Visual C\+\+ .NET でプロジェクトを移行する場合は、DLL、ローカルにインスタンス化されたバージョンからインポート `CString` の競合を対象にインクリメント定義された `CString` については、リンカー シンボルのエラーが表示される可能性があります。  これを行うには、適切な方法です。  この問題の詳細については、MSDN ライブラリ CD\-ROM CString 派生クラス」 \(Q309801\) または [http:\/\/support.microsoft.com\/default.aspx](http://support.microsoft.com/default.aspx)インポートした場合、サポート技術情報の文書は、「"の"エラーをリンクします。  
  
 次のような場合に、リンカーは多重定義されたクラスをシンボルのエラーを生成します。  `CString`\- MFC 拡張 DLL から派生クラスをエクスポート \(`CMyString`\) と仮定する:  
  
 [!CODE [NVC_MFC_DLL#6](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_DLL#6)]  
  
 コンシューマー コードは `CString` と `CMyString`の組み合わせを使用します。"  MyString.h は」プリコンパイル済みヘッダーに含めず、`CString` の使用に表示される `CMyString` はありません。  
  
 別のソース ファイル、Source1.cpp と Source2.cpp で `CString` と `CMyString` のクラスを使用すると仮定します。  Source1.cpp では、`CMyString` と \#include MyString.h を使用します。  Source2.cpp では、`CString`を使用しますが、\#include MyString.h。  この場合、リンカーがある `CStringT` について重複定義されて不平を指定します。  これは `CMyString`をインポート、エクスポート `CStringT` テンプレートを使用してコンパイラが発生 DLL からローカルにインスタンス化する `CString` によって。  
  
 この問題を解決するには、次の操作を行います。:  
  
 MFC90.DLL から `CStringA` と `CStringW` \(および必要な基本クラス\) エクスポートします。  MFC が含まれているプロジェクトは前の MFC 実装のように MFC DLL のエクスポート `CStringA` と、`CStringW`を常に使用します。  
  
 たとえば、次 `CStringT_Exported` が存在する `CStringT` テンプレートを使用してエクスポートの派生クラスを作成する:  
  
 [!CODE [NVC_MFC_DLL#7](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_DLL#7)]  
  
 AfxStr.h では、次のように前の `CString`、`CStringA`と `CStringW` の typedef を置換します:  
  
 [!CODE [NVC_MFC_DLL#8](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_DLL#8)]  
  
 複数の警告があります:  
  
-   これにより `CStringT` の特殊なクラスをエクスポート ATL プロジェクトのみが発生します。`CStringT` 自体をエクスポートすることはできません。  
  
-   `CStringT` からエクスポートの派生クラスを使用して再実装の `CStringT` の機能に抑えられます。  追加のコードは `CStringT` の基本クラスのコンストラクターを転送に制限されます。  
  
-   MFC 共有 DLL と`CString`ビルドすると、`CStringA`と `CStringW` でマークされている `__declspec(dllexport/dllimport)` のみ使用します。  MFC のスタティック リンク ライブラリとエクスポートように、これらのクラスにマークを付ける必要はありません; それ以外の場合は、ユーザーの DLL 内の `CString`、`CStringA`と `CStringW` の内部では、エクスポートように `CString` を示します。  
  
## 関連トピック  
 [CStringT クラス](../atl-mfc-shared/reference/cstringt-class.md)  
  
## 参照  
 [CStringT の使用](../atl-mfc-shared/using-cstringt.md)   
 [CString の使用](../atl-mfc-shared/using-cstring.md)