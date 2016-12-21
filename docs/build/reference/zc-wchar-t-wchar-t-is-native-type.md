---
title: "/Zc:wchar_t (wchar_t をネイティブ型として認識) | Microsoft Docs"
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
  - "VC.Project.VCCLWCECompilerTool.TreatWChar_tAsBuiltInType"
  - "VC.Project.VCCLCompilerTool.TreatWChar_tAsBuiltInType"
  - "/Zc:wchar_t"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Zc コンパイラ オプション [C++]"
  - "準拠コンパイラ オプション"
  - "wchar_t 型"
  - "Zc コンパイラ オプション [C++]"
  - "-Zc コンパイラ オプション [C++]"
ms.assetid: b0de5a84-da72-4e5a-9a4e-541099f939e0
caps.latest.revision: 18
caps.handback.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /Zc:wchar_t (wchar_t をネイティブ型として認識)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`wchar_t` を、C\+\+ 標準に従って組み込み型として解析します。  **\/Zc:wchar\_t** は既定でオンになります。  
  
## 構文  
  
```  
/Zc:wchar_t[-]  
```  
  
## 解説  
 **\/Zc:wchar\_t** がオンの場合、`wchar_t` は Microsoft 固有のネイティブ型 `__wchar_t` に割り当てられます。  **\/Zc:wchar\_t\-** \(マイナス記号付き\) を指定すると、`wchar_t` は `unsigned short` の `typedef` に割り当てられます   \(Visual C\+\+ 6.0 以前では、`wchar_t` は、組み込み型として実装されていたのではなく、`unsigned short` の `typedef` として wchar.h で宣言されていました\)。C\+\+ 標準では `wchar_t` は組み込み型である必要があるため、**\/Zc:wchar\_t\-** はお勧めしません。  `typedef` バージョンを使用すると、移植性の問題が発生することがあります。  以前のバージョンの Visual C\+\+ からアップグレードしているとき、コードが `wchar_t` を `unsigned short` に暗黙的に変換しようとしたために [C2664](../../error-messages/compiler-errors-2/compiler-error-c2664.md) コンパイル エラーが発生した場合は、**\/Zc:wchar\_t\-** を設定するのではなく、コードを変更してエラーを修正することをお勧めします。  
  
 Microsoft では、`wchar_t` が 2 バイトの符号なしの値として実装されます。  `wchar_t` の詳細については、「[データ型の範囲](../../cpp/data-type-ranges.md)」および「[基本型](../../cpp/fundamental-types-cpp.md)」を参照してください。  
  
 `wchar_t` の `typedef` バージョンが使用されている以前のコードと相互運用する必要があるコードを新しく記述する場合は、`wchar_t` の `unsigned short` バリエーションと `__wchar_t` バリエーションの両方に対してオーバーロードを指定できます。これにより、新しいコードは、**\/Zc:wchar\_t** を使用してコンパイルされるコード、または使用せずにコンパイルされるコードとリンクできます。  これ以外の場合は、**\/Zc:wchar\_t** を使用するライブラリ ビルドと、使用しないライブラリ ビルドの 2 つの異なるビルドを指定する必要があります。  この場合も、以前のコードのビルドには、新しいコードをコンパイルするときに使用するコンパイラを使用することをお勧めします。  さまざまなコンパイラでコンパイルされたバイナリを混在させないでください。  
  
 **\/Zc:wchar\_t** を指定すると、**\_WCHAR\_T\_DEFINED** シンボルと **\_NATIVE\_WCHAR\_T\_DEFINED** シンボルが定義されます。  詳細については、「[定義済みマクロ](../../preprocessor/predefined-macros.md)」を参照してください。  
  
 コードでコンパイラ COM グローバル関数が使用されている場合は、**\/Zc:wchar\_t** が既定でオンになったため、[コメント プラグマ](../../preprocessor/comment-c-cpp.md)またはコマンド ラインから comsupp.lib への明示的な参照は、comsuppw.lib または comsuppwd.lib のいずれかへの参照に変更します   \(**\/Zc:wchar\_t\-** でコンパイルする必要がある場合は、comsupp.lib を使用します\)。comdef.h のヘッダー ファイルを含めると、適切なライブラリが自動的に指定されます。  コンパイラ COM サポートについては、「[コンパイラ COM サポート](../Topic/Compiler%20COM%20Support.md)」を参照してください。  
  
 `wchar_t` 型は、C コードをコンパイルするときはサポートされません。  Visual C\+\+ の準拠の問題の詳細については、「[非標準動作](../Topic/Nonstandard%20Behavior.md)」を参照してください。  
  
### Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[プロジェクトのプロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。  
  
2.  左ペインで、**\[構成プロパティ\]**、**\[C\/C\+\+\]** の順に展開し、**\[言語\]** を選択します。  
  
3.  **\[wchar\_t をビルトイン型として扱う\]** プロパティを変更します。  
  
### このコンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.TreatWChar_tAsBuiltInType%2A>」を参照してください。  
  
## 参照  
 [\/Zc \(準拠\)](../../build/reference/zc-conformance.md)