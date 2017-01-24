---
title: "コンパイラの警告 (レベル 2) C4275 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4275"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4275"
ms.assetid: 18de967a-0a44-4dbc-a2e8-fc4c067ba909
caps.latest.revision: 14
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 (レベル 2) C4275
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

DLL インターフェイスではない 'classkey' '識別子' が DLL インターフェイスのベースになる 'classkey' '識別子' として使われています。  
  
 エクスポートされたクラスが、エクスポートされていないクラスから派生しています。  
  
 [\_\_declspec\(dllexport\)](../../cpp/dllexport-dllimport.md) を指定してクラスをエクスポートするときは、データが破損される可能性を最小限に抑えるために、次のことを確認してください。  
  
-   すべての静的データは、DLL からエクスポートされる関数を使用してアクセスされている。  
  
-   クラスのどのインライン メソッドも静的データを変更できない。  
  
-   クラスのどのインライン メソッドも、静的データを使用する CRT 関数または他のライブラリ関数を使用しない。  
  
-   どのインライン クラス関数も、静的データにアクセスするような CRT 関数または他のライブラリ関数を使用しない。  
  
-   EXE および DLL のインスタンス生成で静的データが異なる場合は、インライン展開するかしないかにかかわらず、クラスのどのメソッドも型を使用できない。  
  
 DLL を定義し、仮想関数を使用するクラス、および型のオブジェクトをインスタンス化したり削除したりする場合に呼び出す関数をこの DLL で定義することにより、クラスをエクスポートせずに済みます。この場合、型から仮想関数を呼び出すだけです。  
  
 テンプレートのエクスポートの詳細については、参照します [http:\/\/support.microsoft.com\/default.aspx?scid\=KB;EN\-US;168958](http://support.microsoft.com/default.aspx?scid=KB;EN-US;168958)。  
  
 Visual C\+\+ では、C4275 エラーは、標準 C\+\+ ライブラリの型から派生している場合、デバッグ リリース \(**\/MTd**\) をコンパイルしている場合、およびコンパイラ エラー メッセージが \_Container\_base を参照する場合は無視できます。  
  
```  
// C4275.cpp  
// compile with: /EHsc /MTd /W2 /c  
#include <vector>  
using namespace std;  
class Node;  
class __declspec(dllimport) VecWrapper : vector<Node *> {};   // C4275  
```