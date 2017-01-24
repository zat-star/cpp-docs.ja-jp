---
title: "detect_mismatch | Microsoft Docs"
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
  - "vc-pragma.detect_mismatch"
  - "detect_mismatch_CPP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "detect_mismatch プラグマ"
  - "プラグマ, detect_mismatch"
ms.assetid: ddb13ac9-0e2f-40ce-be69-7e44c04f5a12
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# detect_mismatch
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

オブジェクト内にレコードを配置します。  リンカーは、不一致の可能性を探してこれらのレコードをチェックします。  
  
## 構文  
  
```  
#pragma detect_mismatch( "name", "value"))  
```  
  
## 解説  
 プロジェクトのリンク時に、同じ `name` を持つが `value` がそれぞれ異なる 2 つのオブジェクトがプロジェクトに含まれている場合、リンカーは `LNK2038` エラーをスローします。  整合性のないオブジェクト ファイルのリンクを防止するには、このプラグマを使用します。  
  
 名前と値の両方が文字列リテラルで、エスケープ文字と連結に関して文字列リテラルの規則に準拠します。  これらは大文字と小文字を区別し、コンマ、等号、引用符、または `null` 文字を含めることはできません。  
  
## 使用例  
 この例では、同じバージョン ラベルの異なるバージョン番号を持つ 2 つのファイルを作成します。  
  
```  
// pragma_directive_detect_mismatch_a.cpp  
#pragma detect_mismatch("myLib_version", "9")  
int main ()  
{  
   return 0;  
}  
  
// pragma_directive_detect_mismatch_b.cpp  
#pragma detect_mismatch("myLib_version", "1")  
```  
  
 コマンド ライン `cl pragma_directive_detect_mismatch_a.cpp pragma_directive_detect_mismatch_b.cpp` を使用してこれらの両方のファイルをコンパイルすると、エラー `LNK2038` が表示されます。  
  
## 参照  
 [プラグマ ディレクティブと \_\_Pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)