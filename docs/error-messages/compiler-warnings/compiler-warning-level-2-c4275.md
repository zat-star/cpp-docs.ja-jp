---
title: "コンパイラの警告 (レベル 2) C4275 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4275
dev_langs:
- C++
helpviewer_keywords:
- C4275
ms.assetid: 18de967a-0a44-4dbc-a2e8-fc4c067ba909
caps.latest.revision: 14
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
translationtype: Machine Translation
ms.sourcegitcommit: 3f69f0c3176d2fbe19e11ce08c071691a72d858d
ms.openlocfilehash: 873a96d4595b75ff6b9567500723c32d7ba5bd2b
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-2-c4275"></a>コンパイラの警告 (レベル 2) C4275
非 DLL インターフェイスした '識別子' のベースとして使用した '識別子' の DLL インターフェイス  
  
 エクスポートされたクラスがエクスポートされていないクラスから派生します。  
  
 使用してクラスをエクスポートするときに、データ破損の可能性を最小限に抑える[方式](../../cpp/dllexport-dllimport.md)、いることを確認します。  
  
-   すべての静的データは、DLL からエクスポートされる関数を使用してアクセスします。  
  
-   クラスのインラインのメソッドは静的なデータを変更できません。  
  
-   クラスのメソッドをインライン展開が CRT 関数を使用しないか、他のライブラリ関数が静的データを使用します。  
  
-   インライン関数ではクラスの関数を使用していない CRT 関数、またはその他のライブラリ関数では、静的データにアクセスするなど、します。  
  
-   クラスのメソッドがありません (に関係なくインライン展開) EXE および DLL にインスタンス化と静的データの差異がある型を使用できます。  
  
 インスタンスを作成する仮想関数を持つクラスを定義し、機能する DLL を呼び出すことができますを定義して、型のオブジェクトを削除してクラスをエクスポートする回避できます。  仮想関数を型にのみ呼び出すことができます。  
  
 テンプレートをエクスポートする方法の詳細については、次を参照してください[問題。EN-US;&16895;8](http://support.microsoft.com/default.aspx?scid=KB;EN-US;168958)します。  
  
 デバッグ リリースをコンパイルする C++ 標準ライブラリ内の型から派生した場合は、Visual C で C4275 を無視できます (**/MTd**) し、コンパイラ エラー メッセージは _Container_base を参照します。  
  
```  
// C4275.cpp  
// compile with: /EHsc /MTd /W2 /c  
#include <vector>  
using namespace std;  
class Node;  
class __declspec(dllimport) VecWrapper : vector<Node *> {};   // C4275  
```
