---
title: "char、wchar_t、char16_t、char32_t | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "char_cpp"
  - "char16_t_cpp"
  - "whchar_t_cpp"
  - "char32_t_cpp"
dev_langs: 
  - "C++"
ms.assetid: 6b33e9f5-455b-4e49-8f12-a150cbfe2e5b
caps.latest.revision: 2
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 2
---
# char、wchar_t、char16_t、char32_t
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

型 char、wchar\_t、char16\_t および char32\_t は英数字だけでなく、英数字以外のグリフと印刷されない文字を表す組み込み型です。  char のサイズは 8 ビット、wchar\_t と char16\_t のサイズは 16 ビット、char32\_t のサイズは 32 ビットです。  
  
## 構文  
  
```vb  
char     ch1{ 'a' };  
wchar_t  ch2{ 'a' }; // or {L'a'}  
char16_t ch3{ L'a' };// or {L'a'}  
char32_t ch4{ L'a' };// or {L'a'}  
```  
  
## 解説  
 `char` 型は C および C\+\+ の元の文字型でした。  ASCII 文字セット、またはいずれかの ISO 8859 文字セット、または UTF\-8 文字セットの文字を格納するために使用できます。  `unsigned char` 型は、C\+\+ の組み込み型でない *byte* を表すためにしばしば使用されます。  char 型は、多くの言語でテキストに適していません。  一般に、最新のプログラムでは、テキストを表すためにいずれかのワイド文字型を使用する必要があります。  Unicode は、  
  
 C\+\+ 標準ライブラリでは、basic\_string 型はナロー文字列とワイド文字列の両方に向けて特殊化されています。  文字が char 型の場合は std::string を使用し、文字が wchar\_t 型の場合は std::wstring を使用します。  std::stringstream と std::cout など、テキストを表すその他の型は、ナロー文字列とワイド文字列向けに特殊化されています。  
  
## 必要条件