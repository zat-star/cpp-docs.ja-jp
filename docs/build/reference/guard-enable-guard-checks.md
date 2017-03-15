---
title: "/GUARD (ガード チェックを有効にする) | Microsoft Docs"
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
ms.assetid: 72758e23-70ac-4616-94d7-d767477406d1
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# /GUARD (ガード チェックを有効にする)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

実行可能イメージで、Control Flow Guard のチェックのサポートを指定します。  
  
## 構文  
  
```  
/GUARD:{CF|NO}  
```  
  
## 解説  
 \/GUARD:CF を指定した場合、リンカーは、Control Flow Guard \(CFG\) の実行時チェックをサポートしていることを示すように、.dll または .exe のヘッダーを変更します。  また、リンカーは、必要な制御フローのターゲット アドレス データをヘッダーに追加します。  既定では、\/GUARD:CF は無効です。  \/GUARD:NO を使用して明示的に無効化できます。  有効にするには、\/GUARD:CF が [\/DYNAMICBASE \(ASLR \(Address Space Layout Randomization\) の使用\)](../../build/reference/dynamicbase-use-address-space-layout-randomization.md) リンカーのオプションも必要としますが、既定でオンになっています。  
  
 [\/guard:cf](../../build/reference/guard-enable-control-flow-guard.md) オプションを使用してソース コードをコンパイルしたときに、コンパイラは可能なターゲット アドレスに対するすべての間接呼び出しを確認して、制御フローを分析します。  コンパイラは、間接呼び出し命令のターゲット アドレスが、実行時に既知のターゲット アドレスの一覧にあることを検証するコードを挿入します。  CFG をサポートするオペレーティング システムは、CFG のランタイム チェックに失敗したプログラムを停止します。  これにより、データの破損を利用して呼び出し対象を変更することによって攻撃者が悪意のあるコードを実行することは、より難しくなります。  
  
 \/GUARD:CF オプションは、CFG に対応する実行可能イメージを作成するために、コンパイラとリンカーの両方で指定する必要があります。  \/GUARD:CF を使用してコンパイルされているもののリンクされていないコードでは、実行時チェックのコストが生じますが、CFG 保護を有効にしません。  \/GUARD:CF オプションを `cl` コマンドに指定してコンパイルおよびリンクを 1 つのステップで実行する場合、コンパイラはフラグをリンカーに渡します。  Visual Studio で**Control Flow Guard** プロパティが設定されている場合、\/GUARD:CF オプションが、コンパイラとリンカーの両方に渡されます。  オブジェクトのファイルまたはライブラリが個別にコンパイルされた場合、オプションは`link` コマンドで明示的に指定する必要があります。  
  
### このリンカー オプションを Visual Studio で設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[方法 : プロジェクト プロパティ ページを開く](../../misc/how-to-open-project-property-pages.md)」を参照してください。  
  
2.  **［構成プロパティ］**、**［リンカー］**、**［コマンド ライン］** と展開します。  
  
3.  **\[追加のオプション\]** で、`/GUARD:CF` を入力します。  
  
## 参照  
 [\/guard \(制御フロー ガードを有効にする\)](../../build/reference/guard-enable-control-flow-guard.md)   
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)