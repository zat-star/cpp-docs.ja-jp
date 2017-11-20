---
title: "アセンブリ言語のコメント |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- assembly language [C++], comments
- comments [C++], assembly language
- macros [C++], assembly language
- __asm keyword [C++], instructions
ms.assetid: 0dc10850-77f5-426e-9dab-185ea28e06e4
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 8b93f00aac6151471c1e36b29b2d9f5c3cdbdc1f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="assembly-language-comments"></a>アセンブリ言語のコメント
## <a name="microsoft-specific"></a>Microsoft 固有の仕様  
 」の手順に、`__asm`ブロックは、アセンブリ言語のコメントを使用できます。  
  
```  
__asm mov ax, offset buff ; Load address of buff  
```  
  
 C マクロは、論理の単一行に展開するためは、マクロ内のアセンブリ言語のコメントを使用しないでください。 (を参照してください[_ _asm ブロックの C マクロとして定義](../../assembler/inline/defining-asm-blocks-as-c-macros.md))。`__asm`ブロックすることもできます C スタイルのコメントを含むです。 詳細については、次を参照してください。[を使用して C または C++ _ _asm ブロックで](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md)です。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [__asm ブロックでのアセンブリ言語の使用](../../assembler/inline/using-assembly-language-in-asm-blocks.md)