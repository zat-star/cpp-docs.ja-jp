---
title: "_ _Asm ブロックでの C または C++ シンボルの使用 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- __asm keyword [C++], syntax
- symbols, in __asm blocks
- Visual C, symbols in __asm blocks
- __asm keyword [C++], C/C++ elements in
- Visual C++, in __asm blocks
ms.assetid: 0758ffdc-dfe9-41c8-a5e1-fd395bcac328
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b6a39b747c8c576d148bafff19a664a95fcb43e9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="using-c-or-c-symbols-in-asm-blocks"></a>__asm ブロックでの C または C++ シンボルの使用
## <a name="microsoft-specific"></a>Microsoft 固有の仕様  
 `__asm`ブロックは、ブロックが表示されるスコープ内の C または C++ シンボルを参照できます。 (C および C++ のシンボルは、変数名、関数名、およびラベルである、シンボリック定数のない名前または`enum`メンバー。 できません C++ メンバー関数を呼び出します。)  
  
 C および C++ の記号を使用するいくつかの制限が適用されます。  
  
-   各アセンブリ言語のステートメントには、1 つの C または C++ シンボルのみを含めることができます。 複数のシンボルは、同じアセンブリ命令だけに現れる**長さ**、**型**、および**サイズ**式。  
  
-   参照される関数、`__asm`ブロックは (プロトタイプ) プログラムの前に宣言する必要があります。 それ以外の場合、コンパイラと区別できない関数名のラベル、`__asm`ブロックします。  
  
-   `__asm`ブロック (ケース) に関係なく予約 MASM 単語と同じスペル チェックですべての C または C++ シンボルは使用できません。 MASM の予約語などの命令名**プッシュ**SI などの名前を登録します。  
  
-   構造体と共用体のタグがで認識されない`__asm`ブロックします。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>参照  
 [__asm ブロックでの C または C++ の使用](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md)