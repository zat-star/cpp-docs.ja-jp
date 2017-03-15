---
title: "/vmm、/vms、/vmv (通常の最適化) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/vms"
  - "/vmm"
  - "/vmv"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/vmm コンパイラ オプション [C++]"
  - "/vms コンパイラ オプション [C++]"
  - "/vmv コンパイラ オプション [C++]"
  - "汎用的処理形式のコンパイラ オプション"
  - "Single Inheritance コンパイラ オプション"
  - "仮想継承コンパイラ オプション"
  - "vmm コンパイラ オプション [C++]"
  - "-vmm コンパイラ オプション [C++]"
  - "vms コンパイラ オプション [C++]"
  - "-vms コンパイラ オプション [C++]"
  - "vmv コンパイラ オプション [C++]"
  - "-vmv コンパイラ オプション [C++]"
ms.assetid: 0fcd7ae0-3031-4c62-a2a8-e154c8685dae
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# /vmm、/vms、/vmv (通常の最適化)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[\/vmb、\/vmg \(処理形式\)](../../build/reference/vmb-vmg-representation-method.md) が[処理形式](../../build/reference/vmb-vmg-representation-method.md)として選択されたときに使用します。  これらのオプションは、まだ検出されていないクラス定義の継承モデルを示します。  
  
## 構文  
  
```  
/vmm  
/vms  
/vmv  
```  
  
## 解説  
 これらのオプションの説明を次の表に示します。  
  
|オプション|説明|  
|-----------|--------|  
|**\/vmm**|クラスのメンバーへの最も一般的なポインター表現を多重継承するクラスに対して指定します。<br /><br /> 対応する[継承キーワード](../../cpp/inheritance-keywords.md)および [\#pragma pointers\_to\_members](../Topic/pointers_to_members.md) の引数は **multiple\_inheritance** です。<br /><br /> この表現は、単一継承に必要な表現よりもサイズが大きくなります。<br /><br /> メンバーへのポインターが宣言されているクラス定義の継承モデルが仮想モデルの場合、コンパイラはエラーを出力します。|  
|**\/vms**|クラスのメンバーへの最も一般的なポインター表現を何も継承しないクラスか、単一継承するクラスに対して指定します。<br /><br /> 対応する[継承キーワード](../../cpp/inheritance-keywords.md)および [\#pragma pointers\_to\_members](../Topic/pointers_to_members.md) の引数は **single\_inheritance** です。<br /><br /> これは、クラスのメンバーへのポインターの最小サイズの表現です。<br /><br /> メンバーへのポインターが宣言されているクラス定義の継承モデルが多重継承モデルまたは仮想モデルの場合、コンパイラはエラーを出力します。|  
|**\/vmv**|クラスのメンバーへの最も一般的なポインター表現を仮想継承するクラスに対して指定します。  エラーになることはありません。これは、既定の設定です。<br /><br /> 対応する[継承キーワード](../../cpp/inheritance-keywords.md)および [\#pragma pointers\_to\_members](../Topic/pointers_to_members.md) の引数は **virtual\_inheritance** です。<br /><br /> このオプションは、ポインターを解釈するために、ほかのオプションよりもポインターのサイズが大きくなり、追加コードが必要になります。|  
  
 上のどの継承モデル オプションを選択しても、クラス メンバーを指すすべてのポインターに対してそのモデルが適用されます。継承の種類やポインター宣言の位置 \(クラス定義の前または後ろ\) は関係ありません。  したがって、常に単一継承のクラスを使用している場合は、**\/vms** を使ってコンパイルするとコード サイズが小さくなります。最も一般的な方法でコンパイルするには、 **\/vmv** を使ってコンパイルします。ただし、このオプションではデータ表現が大きくなります。  
  
### Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[方法 : プロジェクト プロパティ ページを開く](../../misc/how-to-open-project-property-pages.md)」を参照してください。  
  
2.  **\[C\/C\+\+\]** フォルダーをクリックします。  
  
3.  **\[コマンド ライン\]** プロパティ ページをクリックします。  
  
4.  **\[追加のオプション\]** ボックスにコンパイラ オプションを入力します。  
  
### このコンパイラ オプションをコードから設定するには  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A> を参照してください。  
  
## 参照  
 [\/vmb、\/vmg \(処理形式\)](../../build/reference/vmb-vmg-representation-method.md)   
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../Topic/Setting%20Compiler%20Options.md)