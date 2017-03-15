---
title: "混合モードから純粋な中間言語へのプロジェクトの変換 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "中間言語, 混合モード アプリケーション"
  - "混合モード アプリケーション"
  - "混合モード アプリケーション, 中間言語"
  - "プロジェクト [C++], 変換 (中間言語に)"
ms.assetid: 855f9e3c-4f09-4bfe-8eab-a45f68292be9
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# 混合モードから純粋な中間言語へのプロジェクトの変換
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

既定では、Visual C\+\+ CLR プロジェクトはすべて、C ランタイム ライブラリにリンクされます。  結果として、これらのプロジェクトは、ネイティブ コードを共通言語ランタイム \(マネージ コード\) を対象としたコードと結合するため、混合モード アプリケーションとして分類されます。  これらをコンパイルすると、Microsoft Intermediate Language \(MSIL\) と呼ばれる中間言語 \(IL\) が生成されます。  
  
### 混合モードのアプリケーションを純粋な中間言語に変換するには  
  
1.  [C ランタイム ライブラリ](../c-runtime-library/crt-library-features.md) \(CRT: C Run\-Time\) へのリンクを削除します。  
  
    1.  アプリケーションのエントリ ポイントが定義されている .cpp ファイルで、エントリ ポイントを `Main()` に変更します。  `Main()` の使用は、プロジェクトを CRT にリンクしないことを示します。  
  
    2.  ソリューション エクスプローラーで、プロジェクトを右クリックし、ショートカット メニューの **\[プロパティ\]** をクリックして、アプリケーションのプロパティ ページを開きます。  
  
    3.  **\[リンカー\]** の **\[詳細\]** プロジェクト プロパティ ページで、**\[エントリ ポイント\]** フィールドをクリックし、「Main」と入力します。  
  
    4.  コンソール アプリケーションの場合は、\[リンカー\] の \[システム\] プロパティ ページで、\[サブシステム\] フィールドをクリックし、その値を \[コンソール \(\/SUBSYSTEM:CONSOLE\)\] に変更します。  
  
        > [!NOTE]
        >  Windows フォーム アプリケーションの場合は、\[サブシステム\] フィールドが既定で \[Windows \(\/SUBSYSTEM:WINDOWS\)\] に設定されているため、このプロパティを設定する必要はありません。  
  
    5.  stdafx.h で、すべての `#include` ステートメントをコメント アウトします。  コンソール アプリケーションの例を次に示します。  
  
        ```  
        // #include <iostream>  
        // #include <tchar.h>  
        ```  
  
         または  
  
         Windows フォーム アプリケーションの例を次に示します。  
  
        ```  
        // #include <stdlib.h>  
        // #include <malloc.h>  
        // #include <memory.h>  
        // #include <tchar.h>  
        ```  
  
    6.  Windows フォーム アプリケーションの場合は、Form1.cpp で、windows.h を参照する `#include` ステートメントをコメント アウトします。  たとえば、次のようになります。  
  
        ```  
        // #include <windows.h>  
        ```  
  
2.  次のコードを stdafx.h に追加します。  
  
    ```  
    #ifndef __FLTUSED__  
    #define __FLTUSED__  
       extern "C" __declspec(selectany) int _fltused=1;  
    #endif  
    ```  
  
3.  すべてのアンマネージ型を削除します。  
  
    1.  [System](https://msdn.microsoft.com/en-us/library/system.appdomainmanager.appdomainmanager.aspx) 名前空間の構造体への参照に置き換えられるすべてのアンマネージ型を置き換えます。  次の表は、一般的なマネージ型を示しています。  
  
        |Structure|説明|  
        |---------------|--------|  
        |[\<caps:sentence id\="tgt24" sentenceid\="84e2c64f38f78ba3ea5c905ab5a2da27" class\="tgtSentence"\>Boolean\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.boolean\(v=vs.140\).aspx)|ブール値を表します。|  
        |[\<caps:sentence id\="tgt26" sentenceid\="40ea57d3ee3c07bf1c102b466e1c3091" class\="tgtSentence"\>Byte\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.byte\(v=vs.140\).aspx)|8 ビット符号なし整数を表します。|  
        |[\<caps:sentence id\="tgt28" sentenceid\="a87deb01c5f539e6bda34829c8ef2368" class\="tgtSentence"\>Char\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.char\(v=vs.140\).aspx)|Unicode 文字を表します。|  
        |[\<caps:sentence id\="tgt30" sentenceid\="dfeaaeb4316477bd556ea5e8c3295887" class\="tgtSentence"\>DateTime\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.datetime.datetime.aspx)|通常、日付や時刻として表現される瞬間を表します。|  
        |[\<caps:sentence id\="tgt32" sentenceid\="bdaa3c20a3e3851599514f7c6be5f62f" class\="tgtSentence"\>10 進数\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.decimal\(v=vs.140\).aspx)|10 進数を表します。|  
        |[\<caps:sentence id\="tgt34" sentenceid\="e8cd7da078a86726031ad64f35f5a6c0" class\="tgtSentence"\>Double\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.double\(v=vs.140\).aspx)|倍精度浮動小数点数を表します。|  
        |[\<caps:sentence id\="tgt36" sentenceid\="1e0ca5b1252f1f6b1e0ac91be7e7219e" class\="tgtSentence"\>Guid\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.guid\(v=vs.140\).aspx)|グローバル一意識別子 \(GUID\) を表します。|  
        |[\<caps:sentence id\="tgt38" sentenceid\="ce80d5ec65b1d2a2f1049eadc100db23" class\="tgtSentence"\>Int16\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.int16\(v=vs.140\).aspx)|16 ビット符号付き整数を表します。|  
        |[\<caps:sentence id\="tgt40" sentenceid\="0241adbbd83925f051b694d40f02747f" class\="tgtSentence"\>Int32\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.int32\(v=vs.140\).aspx)|32 ビット符号付き整数を表します。|  
        |[\<caps:sentence id\="tgt42" sentenceid\="ff9b3f96d37353c528517bc3656a00a8" class\="tgtSentence"\>Int64\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.int64\(v=vs.140\).aspx)|64 ビット符号付き整数を表します。|  
        |[\<caps:sentence id\="tgt44" sentenceid\="7f1db863563907cf33604ed7fad6b111" class\="tgtSentence"\>IntPtr\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.intptr\(v=vs.140\).aspx)|ポインターまたはハンドルを表すときに使用されるプラットフォーム固有の型。|  
        |[\<caps:sentence id\="tgt46" sentenceid\="943756eb7841efcc43b7cd37d7254c76" class\="tgtSentence"\>SByte\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.byte.aspx)|8 ビット符号付き整数を表します。|  
        |[\<caps:sentence id\="tgt48" sentenceid\="dd5c07036f2975ff4bce568b6511d3bc" class\="tgtSentence"\>Single\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.single.aspx)|単精度浮動小数点数を表します。|  
        |[\<caps:sentence id\="tgt50" sentenceid\="90150402997ea9c8dc45cc4d41bb28cb" class\="tgtSentence"\>TimeSpan\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.timespan\(v=vs.140\).aspx)|時間間隔を表します。|  
        |[\<caps:sentence id\="tgt52" sentenceid\="a00ef2ef85ff67b7b39339886f19044f" class\="tgtSentence"\>UInt16\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.uint16\(v=vs.140\).aspx)|16 ビット符号なし整数を表します。|  
        |[\<caps:sentence id\="tgt54" sentenceid\="3de84ad0700f2a1571f633d399e1900e" class\="tgtSentence"\>UInt32\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.uint32\(v=vs.140\).aspx)|32 ビット符号なし整数を表します。|  
        |[\<caps:sentence id\="tgt56" sentenceid\="2e8d31865e5d4b9d8611e1b991baed07" class\="tgtSentence"\>UInt64\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.uint64\(v=vs.140\).aspx)|64 ビット符号なし整数を表します。|  
        |[\<caps:sentence id\="tgt58" sentenceid\="92d74abda31865424016b16e2c806a66" class\="tgtSentence"\>UIntPtr\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.uintptr\(v=vs.140\).aspx)|ポインターまたはハンドルを表すときに使用されるプラットフォーム固有の型。|  
        |[\<caps:sentence id\="tgt60" sentenceid\="cab8111fd0b710a336c898e539090e34" class\="tgtSentence"\>Void\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.void\(v=vs.140\).aspx)|値を返さないメソッドを示します。このメソッドの戻り値の型は void です。|