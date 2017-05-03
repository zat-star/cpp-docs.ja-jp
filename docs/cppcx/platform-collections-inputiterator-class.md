---
title: "Platform::Collections::InputIterator クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::InputIterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "InputIterator クラス"
ms.assetid: ef72eea4-32a9-42b9-8119-ce87dbdcd3be
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 4
---
# Platform::Collections::InputIterator クラス
[!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]から派生したコレクション用の、標準テンプレート ライブラリ InputIterator を提供します。  
  
## 構文  
  
```  
template <  
   typename X  
>  
class InputIterator;  
```  
  
#### パラメーター  
 `X`  
 InputIterator テンプレート クラスの型名。  
  
## メンバー  
  
### パブリック typedef  
  
|名前|説明|  
|--------|--------|  
|`difference_type`|ポインターの相違点 \(ptrdiff\_t\)。|  
|`iterator_category`|入力反復子のカテゴリ \(::std::input\_iterator\_tag\)。|  
|`pointer`|`const` `X` へのポインター|  
|`reference`|`const` `X` への参照|  
|`value_type`|`X` 型名。|  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[InputIterator::InputIterator コンストラクター](../cppcx/inputiterator-inputiterator-constructor.md)|InputIterator クラスの新しいインスタンスを初期化します。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[InputIterator::operator\!\= 演算子](../cppcx/inputiterator-operator-inequality-operator.md)|現在の InputIterator が、指定された InputIterator と等しくないかどうかを示します。|  
|[InputIterator::operator\* 演算子](../cppcx/inputiterator-operator-decrementoperator.md)|現在の InputIterator により指定された要素への参照を取得します。|  
|[InputIterator::operator\+\+ 演算子](../cppcx/inputiterator-operator-increment-operator.md)|現在の InputIterator をインクリメントします。|  
|[InputIterator::operator\=\= 演算子](../cppcx/inputiterator-operator-equality-operator.md)|現在の InputIterator が、指定された InputIterator と等しいかどうかを示します。|  
|[InputIterator::operator\-\> 演算子](../cppcx/inputiterator-operator-arrow-operator.md)|現在の InputIterator により参照される要素のアドレスを取得します。|  
  
## 継承階層  
 `InputIterator`  
  
## 必要条件  
 **ヘッダー:** collection.h  
  
 **名前空間:** Platform::Collections  
  
## 参照  
 [\(NOTINBUILD\) プラットフォーム名前空間](http://msdn.microsoft.com/ja-jp/f3ce3eab-028c-4204-ba9f-9ab8af17c8c4)