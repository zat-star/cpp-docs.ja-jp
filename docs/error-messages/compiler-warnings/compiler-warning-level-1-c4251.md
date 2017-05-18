---
title: "コンパイラの警告 (レベル 1) C4251 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4251
dev_langs:
- C++
helpviewer_keywords:
- C4251
ms.assetid: a9992038-f0c2-4fc4-a9be-4509442cbc1e
caps.latest.revision: 16
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3f69f0c3176d2fbe19e11ce08c071691a72d858d
ms.openlocfilehash: b75c3e6c93c0963a692b210b158339ea5e9eacac
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-c4251"></a>コンパイラの警告 (レベル 1) C4251
'identifier': クラス 'type' を 'type2' クラスのクライアントで使用される dll インターフェイスを持っている必要があります  
  
 使用してクラスをエクスポートするときに、データ破損の可能性を最小限に抑える[方式](../../cpp/dllexport-dllimport.md)、いることを確認します。  
  
-   すべての静的データは、DLL からエクスポートされる関数を使用してアクセスします。  
  
-   クラスのインラインのメソッドは静的なデータを変更できません。  
  
-   クラスのメソッドをインライン展開が CRT 関数を使用しない、またはその他のライブラリ関数が静的データを使用して (を参照してください[潜在的なエラーを渡す境界を越えて CRT オブジェクト DLL](../../c-runtime-library/potential-errors-passing-crt-objects-across-dll-boundaries.md)の詳細)。  
  
-   クラスのメソッドがありません (に関係なくインライン展開) EXE および DLL にインスタンス化と静的データの差異がある型を使用できます。  
  
 インスタンスを作成する仮想関数を持つクラスを定義し、機能する DLL を呼び出すことができますを定義して、型のオブジェクトを削除してクラスをエクスポートする回避できます。  仮想関数を型にのみ呼び出すことができます。  
  
 テンプレートをエクスポートする方法の詳細については、次を参照してください[問題。EN-US;&16895;8](http://support.microsoft.com/default.aspx?scid=KB;EN-US;168958)します。  
  
 デバッグ リリースをコンパイルする C++ 標準ライブラリ内の型から派生した場合、C4251 を無視することができます (**/MTd**) し、コンパイラ エラー メッセージは _Container_base を参照します。  
  
```  
// C4251.cpp  
// compile with: /EHsc /MTd /W2 /c  
#include <vector>  
using namespace std;  
class Node;  
class __declspec(dllimport) VecWrapper : vector<Node *> {};   // C4251  
```
