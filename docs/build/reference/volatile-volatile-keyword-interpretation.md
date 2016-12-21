---
title: "/volatile (volatile キーワードの解釈を) | Microsoft Docs"
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
  - "/volatile:iso"
  - "/volatile:ms"
  - "/volatile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/volatile コンパイラ オプション"
  - "/volatile コンパイラ オプション [C++]"
  - "volatile コンパイラ オプション"
  - "-volatile コンパイラ オプション"
  - "volatile コンパイラ オプション [C++]"
  - "-volatile コンパイラ オプション [C++]"
ms.assetid: 9d08fcc6-5bda-44c8-8151-8d8d54f164b8
caps.latest.revision: 15
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /volatile (volatile キーワードの解釈を)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[volatile](../../cpp/volatile-cpp.md) キーワードの解釈方法を指定します。  
  
## 構文  
  
```  
/volatile:{iso|ms}  
```  
  
## Arguments  
 **\/volatile:iso**  
 ISO 標準の C\+\+ 言語で定義されている、厳密な `volatile` のセマンティックスを選択します。  volatile アクセスでは取得と開放のセマンティックスは保証されていません。  コンパイラが ARM をターゲットとする場合は、これは `volatile` の既定の解釈です。  
  
 **\/volatile:ms**  
 Microsoft 拡張 `volatile` セマンティクスを選択すると、ISO 標準 C\+\+ 言語を超えることを保証するメモリ オーダリングが追加されます。  volatile アクセスでは取得と開放のセマンティックスは保証されます。  ただし、このオプションにより、コンパイラはハードウェアのメモリ バリアを強制的に生成します。これによって ARM および他のメモリ オーダリングの弱いアーキテクチャでは、著しいオーバーヘッドが追加される場合があります。  コンパイラが ARM 以外のプラットフォームをターゲットとする場合は、これは `volatile` の既定の解釈です。  
  
## 解説  
 スレッド間で共有されるメモリを扱うときには、**\/volatile:iso** を明示的な同期プリミティブおよびコンパイラ組み込みと共に使用することを強くお勧めします。  詳細については、「[volatile](../../cpp/volatile-cpp.md)」を参照してください。  
  
 既存のコードを移植するか、またはプロジェクトの途中でこのオプションを変更する場合、[C4746](../../error-messages/compiler-warnings/compiler-warning-c4746.md) の警告を有効にして、セマンティクスの違いによって影響を受けるコードの場所を識別することが役立つ場合があります。  
  
 `#pragma` には、このオプションを制御するための相当するものはありません。  
  
### \/volatile コンパイラ オプションを Visual Studio で設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[方法 : プロジェクト プロパティ ページを開く](../../misc/how-to-open-project-property-pages.md)」を参照してください。  
  
2.  **\[C\/C\+\+\]** フォルダーを選択します。  
  
3.  **\[コマンド ライン\]** プロパティ ページを選択します。  
  
4.  **\[追加オプション\]** ボックスに、`/volatile:iso` か `/volatile:ms` を追加します。  
  
## 参照  
 [volatile](../../cpp/volatile-cpp.md)   
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../Topic/Setting%20Compiler%20Options.md)