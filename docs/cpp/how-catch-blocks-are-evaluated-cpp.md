---
title: "Catch ブロックの評価 (C++) の方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- try-catch keyword [C++], catchable types
- catch keyword [C++], types of catch handlers
- C++ exception handling, catch handlers
- exception handling, catching and deleting exceptions
- types [C++], exception handling
ms.assetid: 202dbf07-8ace-4b3b-b3ae-4b45c275e0b4
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
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
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 1098529effb3a15d8f6260ed7167c5553b226857
ms.contentlocale: ja-jp
ms.lasthandoff: 09/25/2017

---
# <a name="how-catch-blocks-are-evaluated-c"></a>Catch ブロックの評価方法 (C++)
C++ では任意の型の例外をスローすることができますが、一般に std::exception から派生した型をスローすることが推奨されます。 C++ 例外をキャッチできます、**キャッチ**スローされた例外、または任意の種類の例外をキャッチできるハンドラーによって、同じ型を指定するハンドラー。  
  
 スローされる例外の型がクラスである場合、クラスは基底クラスも持つため、その例外は、例外の型の基底クラスを受け入れるハンドラー、および例外の型の基底クラスへの参照を受け入れるハンドラーでキャッチできます。 例外が参照によってキャッチされた場合、それは実際にスローされた例外オブジェクトにバインドされることに注意してください。それ以外の場合は、コピーになります (関数の引数とほぼ同じ)。  
  
 例外がスローされると、次の種類のによってキャッチできます**キャッチ**ハンドラー。  
  
-   任意の型を受け取ることができるハンドラー (省略記号構文を使用)。  
  
-   例外オブジェクトと同じ型を受け入れるハンドラーコピーするになっているため**const**と`volatile`修飾子は無視されます。  
  
-   例外オブジェクトと同じ型への参照を受け入れるハンドラー。  
  
-   参照を受け入れるハンドラー、 **const**または`volatile`例外オブジェクトと同じ型の形式です。  
  
-   例外オブジェクトと同じ型の基底クラスを受け入れるハンドラーコピーであるため**const**と`volatile`修飾子は無視されます。 **キャッチ**基底クラスのハンドラーの前にする必要があります、**キャッチ**派生クラスのハンドラー。  
  
-   例外オブジェクトと同じ型の基底クラスへの参照を受け取るハンドラー。  
  
-   参照を受け入れるハンドラー、 **const**または`volatile`例外オブジェクトと同じ型の基本クラスのフォームです。  
  
-   スローされたポインター オブジェクトが標準的なポインター変換規則によって変換できるポインターを受け取るハンドラー。  
  
 順序**キャッチ**ハンドラーの表示は、重要ではためハンドラーを指定された**を再試行してください**ブロックがその出現順に調べられます。 たとえば、派生クラスのハンドラーの前に基底クラスのハンドラーを配置するとエラーになります。 一致すた後**キャッチ**ハンドラーが見つかると、後続のハンドラーはチェックされません。 その結果、省略記号**キャッチ**ハンドラーは、最後のハンドラーをする必要があります、**を再試行してください**ブロックします。 例:  
  
```  
// ...  
try  
{  
    // ...  
}  
catch( ... )  
{  
    // Handle exception here.  
}  
// Error: the next two handlers are never examined.  
catch( const char * str )  
{  
    cout << "Caught exception: " << str << endl;  
}  
catch( CExcptClass E )  
{  
    // Handle CExcptClass exception here.  
}  
```  
  
 この例では、省略記号で**キャッチ**ハンドラーが唯一のハンドラーが調べられますです。  
  
## <a name="see-also"></a>関連項目  
 [C++ 例外処理](../cpp/cpp-exception-handling.md)
