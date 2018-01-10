---
title: "nothrow (C++) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: nothrow_cpp
dev_langs: C++
helpviewer_keywords:
- __declspec keyword [C++], nothrow
- nothrow __declspec keyword
ms.assetid: 0a475139-459c-4ec6-99e8-7ecd0d7f44a3
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a6200a8207fdf25b533c7db7e05247797592744e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
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
  
## <a name="see-also"></a>参照  
 [_ _declspec](../cpp/declspec.md)   
 [キーワード](../cpp/keywords-cpp.md)