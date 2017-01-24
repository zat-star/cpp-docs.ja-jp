---
title: "_bstr_t クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_bstr_t"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_bstr_t クラス"
  - "BSTR オブジェクト"
  - "BSTR オブジェクト, COM のカプセル化"
ms.assetid: 58841fef-fe21-4a84-aab9-780262b5201f
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _bstr_t クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 `_bstr_t` オブジェクトは、[BSTR データ型](http://msdn.microsoft.com/ja-jp/1b2d7d2c-47af-4389-a6b6-b01b7e915228)をカプセル化します。  このクラスは、**SysAllocString** と **SysFreeString** の関数呼び出しおよびその他の `BSTR` API を必要に応じて使用して、リソースの割り当ておよび解放を管理します。  `_bstr_t` クラスは、参照カウントを使用して過剰なオーバーヘッドを回避します。  
  
### 構築  
  
|||  
|-|-|  
|[\_bstr\_t](../cpp/bstr-t-bstr-t.md)|`_bstr_t` オブジェクトを構築します。|  
  
### 操作  
  
|||  
|-|-|  
|[Assign](../cpp/bstr-t-assign.md)|`BSTR` を `_bstr_t` でラップされた `BSTR` にコピーします。|  
|[Attach](../cpp/bstr-t-attach.md)|`_bstr_t` ラッパーを `BSTR` にリンクします。|  
|[copy](../cpp/bstr-t-copy.md)|カプセル化された `BSTR` のコピーを生成します。|  
|[Detach](../cpp/bstr-t-detach.md)|`_bstr_t` でラップされた `BSTR` を返し、`_bstr_t` から `BSTR` をデタッチします。|  
|[GetAddress](../cpp/bstr-t-getaddress.md)|`_bstr_t` でラップされた `BSTR` を指します。|  
|[GetBSTR](../Topic/_bstr_t::GetBSTR.md)|`_bstr_t` でラップされた `BSTR` の先頭を指します。|  
|[length](../cpp/bstr-t-length.md)|`_bstr_t` の文字数を返します。|  
  
### 演算子  
  
|||  
|-|-|  
|[operator \=](../cpp/bstr-t-operator-equal.md)|既存の `_bstr_t` オブジェクトに新しい値を代入します。|  
|[operator \+\=](../cpp/bstr-t-operator-add-equal-plus.md)|`_bstr_t` の末尾に文字を追加します。|  
|[operator \+](../cpp/bstr-t-operator-add-equal-plus.md)|2 つの文字列を連結します。|  
|[\! 演算子](../cpp/bstr-t-operator-logical-not.md)|カプセル化された `BSTR` が **NULL** 文字列であるかどうかを調べます。|  
|[\=\=、\!\=、\<、\>、\<\=、\>\= 演算子](../cpp/bstr-t-relational-operators.md)|2 つの `_bstr_t` オブジェクトを比較します。|  
|[wchar\_t\* &#124; char\* 演算子](../cpp/bstr-t-wchar-t-star-bstr-t-char-star.md)|カプセル化された Unicode またはマルチバイト `BSTR` オブジェクトへのポインターを抽出します。|  
  
## END Microsoft 固有の仕様  
  
## 要件  
 **ヘッダー:** comutil.h  
  
 **ライブラリ:** comsuppw.lib または comsuppwd.lib \(詳細については、「[\/Zc:wchar\_t \(wchar\_t をネイティブ型として認識\)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md)」を参照\)  
  
## 参照  
 [コンパイラ COM サポート クラス](../cpp/compiler-com-support-classes.md)