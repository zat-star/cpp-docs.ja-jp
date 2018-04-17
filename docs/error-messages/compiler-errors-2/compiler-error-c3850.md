---
title: コンパイラ エラー C3850 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: error-reference
f1_keywords:
- C3850
dev_langs:
- C++
helpviewer_keywords:
- C3850
ms.assetid: 028f3a37-f3ad-4ebc-9168-3cdea47524d4
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f5c79f1ab90348ea234e006ae6838d5e80e46c3e
ms.sourcegitcommit: 770f6c4a57200aaa9e8ac6e08a3631a4b4bdca05
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2018
---
# <a name="compiler-error-c3850"></a>コンパイラ エラー C3850
'char': ユニバーサル文字名が正しくない文字を指定しています  
  
 ユニバーサル文字名として表す文字は、0 ～ 10FFFF の範囲の有効な Unicode コード ポイントを表す必要があります。 ユニバーサル文字名に、D800 ～ DFFF の Unicode サロゲート範囲内の値またはエンコードされたサロゲート ペアを含めてはいけません。 コンパイラは、有効なコード ポイントから自動的にサロゲート ペアを生成します。  
  
 C としてコンパイルされたコードでは、0024 ('$')、0040 ('@')、および 0060 ('`') を除き、0000 ～ 009F の範囲内 (境界を含む) の文字を表すユニバーサル文字名を使用してはいけません。  
  
 C++ としてコンパイルされたコードでは、文字列または文字リテラル内に、有効な Unicode コード ポイントのユニバーサル文字名を使用できます。 リテラルを除き、0000 ～ 001F または 007F ～ 009F の範囲内 (境界を含む) の制御文字、あるいは、基本ソース文字セットのメンバーを表すユニバーサル文字名を使用してはいけません。  詳細については、次を参照してください。[文字セット](../../cpp/character-sets.md)です。  
  
## <a name="example"></a>例  
 次の例では、C3850 を発生させ、その修正方法を示しています。  
  
```cpp  
// C3850.cpp  
int main() {  
   int \u0019 = 0;   // C3850, not in allowed range for an identifier  
   const wchar_t * wstr_bad  = L"\UD840DC8A"; // C3850, UCN is surrogate pair  
   const wchar_t * wstr_good = L"\U0002008A"; // Okay, UCN is valid code point  
}  
```