---
title: "リンカ ツール エラー LNK1179 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK1179"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1179"
ms.assetid: 4b1536d7-0d3d-4f29-a9c1-6fa5cf6cb665
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# リンカ ツール エラー LNK1179
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ファイルが無効か、または壊れています : COMDAT 'filename' を複製します。  
  
 オブジェクト モジュールには、同じ名前の COMDAT が 2 つ以上あります。  
  
 このエラーは、外部名の長さを制限する [\/H](../../build/reference/h-restrict-length-of-external-names.md) オプションと、関数を COMDAT にパッケージ化する[\/Gy](../../build/reference/gy-enable-function-level-linking.md) オプションを使用していることが原因で発生する場合があります。  
  
## 使用例  
 次のコードで、`function1` と `function2` の最初の 8 文字は同じです。  この内容を **\/Gy** と **\/H8** を指定してコンパイルすると、リンク エラーになります。  
  
```  
void function1(void);  
void function2(void);  
  
int main() {  
    function1();  
    function2();  
}  
  
void function1(void) {}  
void function2(void) {}  
```