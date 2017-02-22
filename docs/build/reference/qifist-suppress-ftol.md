---
title: "/QIfist (_ftol を呼び出さない) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/qifist"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "QIfist コンパイラ オプション [C++]"
  - "-QIfist コンパイラ オプション [C++]"
  - "/QIfist コンパイラ オプション [C++]"
ms.assetid: 1afd32a5-f658-4b66-85f4-e0ce4cb955bd
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# /QIfist (_ftol を呼び出さない)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

浮動小数点型から整数型への変換が必要なときには、ヘルパー関数 `_ftol` を呼び出しません。  
  
## 構文  
  
```  
/QIfist  
```  
  
## 解説  
  
> [!NOTE]
>  **\/QIfist** は x86 に対応するコンパイラでのみ使用できます。このコンパイラ オプションは [!INCLUDE[vcprx64](../Token/vcprx64_md.md)] や ARM に対応するコンパイラでは使用できません。  
  
 `_ftol` 関数では、浮動小数点型から整数型への変換に加えて、浮動小数点制御ワードのビット 10 と 11 を設定して、FPU \(Floating\-Point Unit\) の丸めモードをゼロ \(切り捨て\) にします。  したがって、浮動小数点型から整数型への変換は、ANSI C 規格どおりに行われ、小数部分を破棄することが保証されます。  **\/QIfist** を使用すると、この保証が適用されません。  丸めモードは、Intel 社のリファレンス マニュアルに示されたとおり、次の 4 とおりのうちのいずれかになります。  
  
-   一番近い値に丸める \(中間の場合は偶数\)。  
  
-   負の無限大に丸める。  
  
-   正の無限大に丸める。  
  
-   ゼロに丸める。  
  
 C のランタイム関数 [\_control87、\_controlfp、\_\_control87\_2](../Topic/_control87,%20_controlfp,%20__control87_2.md) を使用して、FPU の丸め動作を変更できます。  FPU の既定の丸めモードでは、一番近い値に丸められます。**\/QIfist** を使用すると、アプリケーションのパフォーマンスが向上しますが、それにはリスクが伴います。  稼動環境で **\/QIfist** を使ってビルドしたコードを使用する場合は、その前に、丸めモードの影響を受けるコード部分を十分にテストする必要があります。  
  
 [\/arch \(x86\)](../../build/reference/arch-x86.md) と **\/QIfist** は、同じコンパイル単位では使用できません。  
  
> [!NOTE]
>  ビットの丸め動作により、すべての計算の後で浮動小数点も丸められるため、**\/QIfist** は既定で無効です。このため、C スタイルの丸め \(つまりゼロに丸める\) のフラグを設定すると、浮動小数点の計算が異なる場合があります。  浮動小数点数の小数部分の切り捨てについて予想される動作にコードが依存する場合は、**\/QIfist** を使用しないでください。  不明な場合は、**\/QIfist** を使用しないでください。  
  
 **\/QIfist** は使用されなくなりました。  浮動小数点型から整数型への変換処理の速度が飛躍的に向上しました。  詳細については、「[Deprecated Compiler Options in Visual C\+\+ 2005](http://msdn.microsoft.com/ja-jp/aa59fce3-50b8-4f66-9aeb-ce09a7a84cce)」を参照してください。  
  
### Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[方法 : プロジェクト プロパティ ページを開く](../../misc/how-to-open-project-property-pages.md)」を参照してください。  
  
2.  **\[C\/C\+\+\]** フォルダーをクリックします。  
  
3.  **\[コマンド ライン\]** プロパティ ページをクリックします。  
  
4.  \[追加のオプション\]ボックスにコンパイラ オプションを入力します。  
  
### このコンパイラ オプションをコードから設定するには  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A> を参照してください。  
  
## 参照  
 [\/Q オプション \(低水準の操作\)](../../build/reference/q-options-low-level-operations.md)   
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../Topic/Setting%20Compiler%20Options.md)