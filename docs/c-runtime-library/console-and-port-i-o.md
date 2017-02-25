---
title: "コンソール入出力とポート入出力 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.io"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "I/O [CRT], コンソール"
  - "I/O [CRT], ポート"
  - "I/O ルーチン, コンソール入出力とポート入出力"
  - "ポート, I/O ルーチン"
  - "ルーチン"
  - "ルーチン, コンソール入出力とポート入出力"
ms.assetid: 0eee1c92-9b3d-41e0-a43a-257e546eeec8
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# コンソール入出力とポート入出力
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

これらのルーチンは、コンソールまたは指定したポートで読み取ったり書き込んだりします。  コンソール I\/O ルーチンは、ストリーム I\/O または低水準 I\/O のライブラリ ルーチンと互換性がありません。  コンソールまたはポートを開く必要がないまたは I\/O が実行される前に終了したため、このカテゴリに開くまたは終わりルーチンがありません。  Windows オペレーティング システムでは、これらの関数の出力をコンソールに送信され、リダイレクトすることはできません。  
  
### コンソールとポート I\/O ルーチン  
  
|ルーチン|使用方法|  
|----------|----------|  
|[\_cgets、\_cgetws](../c-runtime-library/cgets-cgetws.md)、[\_cgets\_s、\_cgetws\_s](../Topic/_cgets_s,%20_cgetws_s.md)|コンソールから読み取られた文字列|  
|[\_cprintf、\_cwprintf](../c-runtime-library/reference/cprintf-cprintf-l-cwprintf-cwprintf-l.md)、[\_cprintf\_s、\_cprintf\_s\_l、\_cwprintf\_s、\_cwprintf\_s\_l](../c-runtime-library/reference/cprintf-s-cprintf-s-l-cwprintf-s-cwprintf-s-l.md)|コンソールに書式付きデータを書き込みます。|  
|[\_cputs](../Topic/_cputs,%20_cputws.md)|コンソールに文字列を書き込みます。|  
|[\_cscanf、\_cwscanf](../c-runtime-library/reference/cscanf-cscanf-l-cwscanf-cwscanf-l.md)、[\_cscanf\_s、\_cscanf\_s\_l、\_cwscanf\_s、\_cwscanf\_s\_l](../c-runtime-library/reference/cscanf-s-cscanf-s-l-cwscanf-s-cwscanf-s-l.md)|コンソールから書式付きデータを読み込みます。|  
|[\_getch、\_getwch](../Topic/_getch,%20_getwch.md)|コンソールから文字を読み取ります。|  
|[\_getche、\_getwche](../Topic/_getch,%20_getwch.md)|コンソールから文字を読み取ったりエコーします。|  
|[\_inp](../c-runtime-library/inp-inpw-inpd.md)|指定した I\/O ポートから 1 バイトを読み取ります。|  
|[\_inpd](../c-runtime-library/inp-inpw-inpd.md)|指定した I\/O ポートからダブル ワードを読み取ります。|  
|[\_inpw](../c-runtime-library/inp-inpw-inpd.md)|指定した I\/O ポートから 2 バイト"を参照してください。|  
|[\_kbhit](../c-runtime-library/reference/kbhit.md)|コンソールのキーストロークを探します; コンソールから読み取る前に使用します。|  
|[\_outp](../Topic/_outp,%20_outpw,%20_outpd.md)|1 バイト指定 I\/O ポートを記述します。|  
|[\_outpd](../Topic/_outp,%20_outpw,%20_outpd.md)|ダブル ワード指定 I\/O ポートを記述します。|  
|[\_outpw](../Topic/_outp,%20_outpw,%20_outpd.md)|Word 指定 I\/O ポートを記述します。|  
|[\_putch、\_putwch](../Topic/_putch,%20_putwch.md)|コンソールに文字を書き込みます。|  
|[\_ungetch、\_ungetwch](../c-runtime-library/reference/ungetch-ungetwch-ungetch-nolock-ungetwch-nolock.md)|したがって、コンソールから「Unget」の最後に読み取られた文字は次に読み取られた文字になります。|  
  
## 参照  
 [入出力](../Topic/Input%20and%20Output.md)   
 [カテゴリ別ランタイム ルーチン](../c-runtime-library/run-time-routines-by-category.md)