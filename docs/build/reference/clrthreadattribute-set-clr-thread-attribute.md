---
title: "/CLRTHREADATTRIBUTE (CLR スレッド属性の設定) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.CLRThreadAttribute"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/CLRTHREADATTRIBUTE リンカー オプション"
  - "-CLRTHREADATTRIBUTE リンカー オプション"
ms.assetid: 4907e9ef-5031-446c-aecf-0a0b32fae1e8
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# /CLRTHREADATTRIBUTE (CLR スレッド属性の設定)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

CLR プログラムのエントリ ポイントにスレッド処理属性を明示的に指定します。  
  
## 構文  
  
```  
/CLRTHREADATTRIBUTE:{STA|MTA|NONE}  
```  
  
#### パラメーター  
 MTA  
 MTAThreadAttribute 属性をプログラムのエントリ ポイントに適用します。  
  
 NONE  
 \/CLRTHREADATTRIBUTE を指定しないことと同じです。共通言語ランタイム \(CLR: Common Language Runtime\) が既定のスレッド処理属性を設定するようにします。  
  
 STA  
 STAThreadAttribute 属性をプログラムのエントリ ポイントに適用します。  
  
## 解説  
 スレッド属性はメイン スレッドのエントリ ポイントに影響を与えるものであるため、この属性の設定が有効なのは .exe をビルドするときだけです。  
  
 既定のエントリ ポイント \(main または wmain など\) を使用する場合は、\/CLRTHREADATTRIBUTE を使用するか、または既定のエントリ関数にスレッド処理属性 \(STAThreadAttribute または MTAThreadAttribute\) を指定するかして、スレッド処理モデルを指定します。  
  
 既定以外のエントリ ポイントを使用する場合は、\/CLRTHREADATTRIBUTE を使用するか、または既定以外のエントリ関数にスレッド処理属性を指定するかして、スレッド処理モデルを指定します。次に、[\/ENTRY](../../build/reference/entry-entry-point-symbol.md) を使用して、既定以外のエントリ ポイントを指定します。  
  
 ソース コードで指定されたスレッド処理モデルが \/CLRTHREADATTRIBUTE で指定されたスレッド処理モデルと一致しない場合、リンカーは \/CLRTHREADATTRIBUTE を無視し、ソース コードで指定されたスレッド処理モデルを適用します。  
  
 たとえば、シングルスレッドを使用する COM オブジェクトを CLR プログラムでホストする場合は、シングルスレッドを使用する必要があります。マルチスレッドを使用する CLR プログラムでは、シングルスレッドを使用する COM オブジェクトをホストできません。  
  
### Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[方法 : プロジェクト プロパティ ページを開く](../../misc/how-to-open-project-property-pages.md)」を参照してください。  
  
2.  **\[構成プロパティ\]** ノードを展開します。  
  
3.  **\[リンカー\]** ノードを展開します。  
  
4.  **\[詳細\]** プロパティ ページをクリックします。  
  
5.  **\[CLR スレッド属性\]** プロパティを変更します。  
  
### このリンカーをコードから設定するには  
  
1.  「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.CLRThreadAttribute%2A>」を参照してください。  
  
## 参照  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)