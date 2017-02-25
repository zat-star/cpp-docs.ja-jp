---
title: "コンパイラの警告 (レベル 1) C4251 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4251"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4251"
ms.assetid: a9992038-f0c2-4fc4-a9be-4509442cbc1e
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# コンパイラの警告 (レベル 1) C4251
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : class 'type' は \_\_export キーワードを使って class 'type2' にエクスポートしてください。  
  
 [\_\_declspec\(dllexport\)](../../cpp/dllexport-dllimport.md) を指定してクラスをエクスポートするときは、データが破損される可能性を最小限に抑えるために、次のことを確認してください。  
  
-   すべての静的データは、DLL からエクスポートされる関数からアクセスされる。  
  
-   クラスのどのインライン メソッドも静的データを変更できない。  
  
-   クラスのどのインライン メソッドも、静的データを使用する CRT 関数または他のライブラリ関数を使用しない \(詳細については、「[DLL の境界を越えて CRT オブジェクトを渡す場合に発生する可能性のあるエラー](../../c-runtime-library/potential-errors-passing-crt-objects-across-dll-boundaries.md)」を参照してください\)。  
  
-   EXE および DLL のインスタンス生成で静的データが異なる場合は、インライン展開するかしないかにかかわらず、クラスのどのメソッドも型を使用できない。  
  
 DLL を定義し、仮想関数を使用するクラス、および型のオブジェクトをインスタンス化したり削除したりする場合に呼び出す関数をこの DLL で定義することにより、クラスをエクスポートせずに済みます。この場合、型から仮想関数を呼び出すだけです。  
  
 テンプレートのエクスポートの詳細については、参照します [http:\/\/support.microsoft.com\/default.aspx?scid\=KB;EN\-US;168958](http://support.microsoft.com/default.aspx?scid=KB;EN-US;168958)。  
  
 C4251 エラーは、標準 C\+\+ ライブラリの型から派生している場合、デバッグ リリース \(**\/MTd**\) をコンパイルしている場合、およびコンパイラ エラー メッセージが \_Container\_base を参照する場合は無視できます。  
  
```  
// C4251.cpp  
// compile with: /EHsc /MTd /W2 /c  
#include <vector>  
using namespace std;  
class Node;  
class __declspec(dllimport) VecWrapper : vector<Node *> {};   // C4251  
```