---
title: "nothrow (C++) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- nothrow_cpp
- nothrow
dev_langs:
- C++
helpviewer_keywords:
- __declspec keyword [C++], nothrow
- nothrow __declspec keyword
ms.assetid: 0a475139-459c-4ec6-99e8-7ecd0d7f44a3
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
ms.openlocfilehash: c74490229e2ef54e7947f5e8fedda6057ecccb70
ms.contentlocale: ja-jp
ms.lasthandoff: 09/25/2017

---
# <a name="nothrow-c"></a>nothrow (C++)
**Microsoft 固有の仕様**  
  
 関数の宣言に使用できる `__declspec` 拡張属性。  
  
## <a name="syntax"></a>構文  
  
```  
  
return-type __declspec(nothrow) [call-convention] function-name ([argument-list])  
```  
  
## <a name="remarks"></a>コメント  
 この属性は、宣言された関数、および、その呼び出す関数が例外をスローしないことをコンパイラに伝えます。 同期例外処理モデル (現在は既定のモデル) の場合、コンパイラはこのような関数で特定のアンワインド可能オブジェクトの有効期間を追跡する機構を削除して、コード サイズを大幅に小さくできます。 次のプリプロセッサ ディレクティブを指定した場合、その下の 3 つの関数宣言は等価です。  
  
```  
#define WINAPI __declspec(nothrow) __stdcall   
  
void WINAPI f1();  
void __declspec(nothrow) __stdcall f2();  
void __stdcall f3() throw();  
```  
  
 `void __declspec(nothrow) __stdcall f2();` を使用すると、`#define` ステートメントで示されるような API 定義を使用して、一連の関数で簡単に `nothrow` を指定できるという利点があります。 3 番目の宣言 `, void __stdcall f3() throw();` は C++ 標準で定義されている構文です。  
  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [_ _declspec](../cpp/declspec.md)   
 [キーワード](../cpp/keywords-cpp.md)
