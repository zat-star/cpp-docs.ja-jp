---
title: "インライン アセンブラーの長所 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- assembler [C++], advantages
- inline assembly [C++], about inline assembly
- inline assembly [C++], using
ms.assetid: 94364d97-faa7-4bdf-8473-570956986c51
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 60b8d458212cd2175f2460c1382ed7f8c2c269bb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="advantages-of-inline-assembly"></a>インライン アセンブラーの長所
## <a name="microsoft-specific"></a>Microsoft 固有の仕様  
 インライン アセンブラーは別のアセンブリとリンクの手順を必要としないので、別のアセンブラーより便利です。 インライン アセンブラー コードでは、スコープ内にある C 変数や関数名を使用できるので、プログラムの C コードと簡単に統合できます。 アセンブリ コードが C または C++ ステートメントでインラインを混在させることができます、ために、煩雑であるか、または C または C++ で不可能であるタスクを実行できます。  
  
 インライン アセンブリの使用は、次のとおりです。  
  
-   関数のアセンブリ言語で記述します。  
  
-   コードの速度クリティカル セクションをスポットを最適化します。  
  
-   デバイス ドライバーのハードウェアに直接アクセスを確立しています。  
  
-   「生」の呼び出しのためのプロローグおよびエピローグのコードを記述します。  
  
 インライン アセンブラーは、特殊なツールです。 異なるコンピューターにアプリケーションを移植する場合は、異なるモジュールでコンピューター固有のコードを配置するあります可能性があります。 インライン アセンブラーは、すべての Microsoft マクロ アセンブラーの (MASM) をサポートしないため、マクロとデータのディレクティブする可能性があります方がより便利 MASM モジュールを使用するようにします。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>参照  
 [インライン アセンブラー](../../assembler/inline/inline-assembler.md)