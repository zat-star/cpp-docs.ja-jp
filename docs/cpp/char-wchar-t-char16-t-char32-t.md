---
title: "char、wchar_t、char16_t、char32_t |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- char_cpp
- char16_t_cpp
- wchar_t_cpp
- char32_t_cpp
dev_langs: C++
ms.assetid: 6b33e9f5-455b-4e49-8f12-a150cbfe2e5b
caps.latest.revision: "2"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c01d4718bbc1781ea4705945bb90874384e09058
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="char-wchart-char16t-char32t"></a>char、wchar_t、char16_t、char32_t
型 char、wchar_t、char16_t および char32_t は英数字だけでなく、英数字以外のグリフと印刷されない文字を表す組み込み型です。 char のサイズは 8 ビット、wchar_t と char16_t のサイズは 16 ビット、char32_t のサイズは 32 ビットです。  
  
## <a name="syntax"></a>構文  
  
```cpp  
char     ch1{ 'a' };    
wchar_t  ch2{ 'a' }; // or {L'a'}    
char16_t ch3{ L'a' };// or {L'a'}    
char32_t ch4{ L'a' };// or {L'a'}  
```  
  
## <a name="remarks"></a>コメント  
 `char` 型は C および C++ の元の文字型でした。 ASCII 文字セット、またはいずれかの ISO 8859 文字セット、または UTF-8 文字セットの文字を格納するために使用できます。 型`unsigned char`を表すため多くの場合、*バイト*を C++ では組み込み型ではありません。 char 型は、多くの言語でテキストに適していません。 一般に、最新のプログラムでは、テキストを表すためにいずれかのワイド文字型を使用する必要があります。 Unicode は、  
  
 C++ 標準ライブラリでは、basic_string 型はナロー文字列とワイド文字列の両方に向けて特殊化されています。 文字が char 型の場合は std::string を使用し、文字が wchar_t 型の場合は std::wstring を使用します。 std::stringstream と std::cout など、テキストを表すその他の型は、ナロー文字列とワイド文字列向けに特殊化されています。  
  
