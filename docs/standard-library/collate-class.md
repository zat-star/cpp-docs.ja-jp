---
title: "collate クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::collate"
  - "locale/std::collate"
  - "std.collate"
  - "collate"
  - "Collate"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "collate クラス"
ms.assetid: 92168798-9628-4a2e-be6e-fa62dcd4d6a6
caps.latest.revision: 18
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# collate クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

文字列内の文字の順序付けとグループ化、文字列内の文字の比較、および文字列のハッシュ化を制御するためのロケール ファセットとして使用できるオブジェクトを表すテンプレート クラス。  
  
## 構文  
  
```  
template <class CharType >  
   class collate : public locale::facet;  
```  
  
#### パラメーター  
 `CharType`  
 文字をエンコードするためにプログラム内で使用される型。  
  
## 解説  
 すべてのロケールのファセットと同様、静的オブジェクト ID に最初に格納されている値は 0 です。  格納されている値に初めてアクセスしようとすると、**id** に一意の正の値が格納されます。一部の言語では、複数の文字が 1 文字のように処理され、また別の言語では、個々の文字が 2 文字であるかのように処理されます。  照合クラスが提供する照合サービスは、これらの状況で文字を並べ替える方法を示します。  
  
### コンストラクター  
  
|||  
|-|-|  
|[collate](../Topic/collate::collate.md)|文字列の並べ替え規則を処理するためにロケールのファセットとして機能する `collate` クラスのオブジェクトのコンストラクター。|  
  
### Typedef  
  
|||  
|-|-|  
|[char\_type](../Topic/collate::char_type.md)|`CharType` 型の文字を表す型。|  
|[string\_type](../Topic/collate::string_type.md)|`CharType` 型の文字を格納する `basic_string` 型の文字列を表す型。|  
  
### メンバー関数  
  
|||  
|-|-|  
|[compare](../Topic/collate::compare.md)|等値または非等値のファセット固有の規則に従って、2 文字シーケンスを比較します。|  
|[do\_compare](../Topic/collate::do_compare.md)|等値または非等値のファセット固有の規則に従って、2 文字シーケンスを比較するために呼び出される仮想関数。|  
|[do\_hash](../Topic/collate::do_hash.md)|ファセット固有の規則に従ってシーケンスのハッシュ値を決定するために呼び出される仮想関数。|  
|[do\_transform](../Topic/collate::do_transform.md)|ロケールの文字シーケンスを、同じロケールから同様に変換された他の文字シーケンスとの辞書式の比較で使用できる文字列に変換するために呼び出される仮想関数。|  
|[hash](../Topic/collate::hash.md)|ファセット固有の規則に従ってシーケンスのハッシュ値を決定します。|  
|[変換](../Topic/collate::transform.md)|ロケールの文字シーケンスを、同じロケールから同様に変換された他の文字シーケンスとの辞書式の比較で使用できる文字列に変換します。|  
  
## 必要条件  
 **ヘッダー:** \<locale\>  
  
 **名前空間:** std  
  
## 参照  
 [\<locale\>](../standard-library/locale.md)   
 [C\+\+ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)