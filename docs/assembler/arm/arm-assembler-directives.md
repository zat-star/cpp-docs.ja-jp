---
title: "ARM Assembler Directives | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 9cfa8896-ec10-4e77-855a-3135c40d7d2a
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# ARM Assembler Directives
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

第 7 章に記載されている、ARM アセンブリ言語、ほとんどの部分は、マイクロソフトの ARM アセンブラーを使用して、 [ARM アセンブラー ツール ガイド](http://go.microsoft.com/fwlink/?LinkId=246102)。  ただし、マイクロソフトの実装の一部アセンブリ ディレクティブからの ARM アセンブリ ディレクティブとは異なります。  ここでの相違点について説明します。  
  
## マイクロソフトの実装の ARM アセンブリ ディレクティブ  
 エリア  
 Microsoft の ARM アセンブラーがこれらの領域の属性をサポートしています: 配置、コード、CODEALIGN、データ、NOINIT、読み取り専用、書き込み、サム、腕。  
  
 親指と腕を除くすべてのマニュアルの説明に従って作業を[ARM アセンブラー ツール ガイド](http://go.microsoft.com/fwlink/?LinkId=246102)。  
  
 マイクロソフトの ARM アセンブラーでは、つまみコード セクション親指のコードが含まれているコードのセクションを既定でことを示します。  ARMは、セクション ARMのコードが含まれていることを示します。  
  
 ATTR  
 サポートされていません。  
  
 CODE16  
 マイクロソフトの ARM アセンブラーで許可されていない事前 UAL 親指の構文、意味を含むためにはサポートされません。  サム ディレクティブではなく、と共に UAL の構文を使用します。  
  
 一般的です  
 共通領域の配置の仕様はサポートされていません。  
  
 DCDO  
 サポートされていません。  
  
 DN、QN、SN  
 タイプか、レーン レジスタ エイリアスの仕様はサポートされていません。  
  
 エントリ  
 サポートされていません。  
  
 EQU  
 定義されたシンボルの種類を指定することはできません。  
  
 エクスポートおよびグローバル  
 ```  
  
EXPORTsym {[type]}  
  
```  
  
 `sym`エクスポートするシンボルです。  `[type]`、を指定する場合は、いずれかにすることができます`[DATA]`シンボル データを指していることを示すためにまたは`[FUNC]`シンボルがコードを指していることを示します。  
  
 シノニムのエクスポートはグローバルです。  
  
 EXPORTAS  
 サポートされていません。  
  
 フレーム  
 サポートされていません。  
  
 関数およびプロシージャ  
 アセンブリ構文独自の仕様をサポートしていますが呼び出し元保存し、保存、呼び出し先は、レジスタをリストすることによって上のプロシージャを呼び出し規約マイクロソフトの ARM アセンブラー構文を受け付けますが、レジスタの一覧を無視します。  アセンブラーによって生成されるデバッグ情報の既定の呼び出し規約をサポートしています。  
  
 インポートおよび EXTERN  
 ```  
  
IMPORT sym{, WEAK alias{, TYPE t}}  
  
```  
  
 `sym`インポートするシンボルの名前です。  
  
 弱い場合`alias`が指定されて、そのことを示します`sym` 、弱い外部です。  リンク時に、それを定義が見つからないかどうかへの参照がすべてではなくバインド`alias`。  
  
 場合型 `t` 、次に指定される`t`を解決するリンカーを試みる必要がある方法を示す`sym`。  これらの値は`t`が可能です。   
1： ライブラリの検索を実行しないでください`sym`   
2： ライブラリの検索を実行`sym`   
3\-`sym`用のエイリアスが`alias` \(既定値\)  
  
 EXTERN ではインポート、シノニムを除く`sym`がある場合のみで、現在のアセンブリへの参照をインポートします。  
  
 MACRO  
 マクロの条件コードを保持する変数の使用はサポートされていません。  マクロのパラメーターがサポートされていない場合の既定値。  
  
 NOFP  
 サポートされていません。  
  
 選択すると、TTL、SUBT  
 マイクロソフトの ARM アセンブラー一覧は生成されませんのでサポートされません。  
  
 PRESERVE8  
 サポートされていません。  
  
 再配置  
 `RELOC n`のみ、命令またはデータ定義ディレクティブを実行します。  「再配置することができます匿名のシンボル」はありません。  
  
 必要とします。  
 サポートされていません。  
  
 REQUIRE8  
 サポートされていません。  
  
 THUMBX  
 Microsoft の ARM アセンブラー、サム 2EE の命令セットをサポートしていないために、サポートされません。  
  
## 参照  
 [ARM Assembler Command\-Line Reference](../../assembler/arm/arm-assembler-command-line-reference.md)   
 [ARM Assembler Diagnostic Messages](../../assembler/arm/arm-assembler-diagnostic-messages.md)