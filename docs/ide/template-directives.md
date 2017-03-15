---
title: "テンプレート ディレクティブ | Microsoft Docs"
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
  - "[!else] テンプレート ディレクティブ"
  - "[!endif] テンプレート ディレクティブ"
  - "[!endloop] テンプレート ディレクティブ"
  - "[!if] テンプレート ディレクティブ"
  - "[!loop] テンプレート ディレクティブ"
  - "[!output] テンプレート ディレクティブ"
  - "カスタム ウィザード, template ディレクティブ"
  - "ディレクティブ, template ディレクティブ"
  - "else ディレクティブ ([!else])"
  - "endif ディレクティブ ([!endif])"
  - "endloop ディレクティブ ([!endloop])"
  - "if ディレクティブ ([!if])"
  - "loop ディレクティブ ([!loop])"
  - "output ディレクティブ ([!output])"
  - "template ディレクティブ"
ms.assetid: b6204153-813a-423c-b044-e39c352cc5af
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# テンプレート ディレクティブ
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ウィザードの[テンプレート ファイル](../ide/template-files.md)や [Templates.inf ファイル](../Topic/Templates.inf%20File.md)で次のテンプレート ディレクティブを使用すると、ウィザードをカスタマイズできます。  
  
|ディレクティブ|Description|  
|-------------|-----------------|  
|\[\!  if \]|条件をチェックするための制御構造を開始します。|  
|\[\!  else \]|\[ \!if \] 制御構造の  if \] 制御構造の定義を終了します。  もう 1 つの条件をチェックします。|  
|\[\!  endif \]|\[\!  if \] 制御構造の定義を終了します。|  
|\[\!  output \]|次の 2 つの方法で使用できます。<br /><br /> -   \[\!  output "string" \] で文字列を出力します。<br />-   \[\!  output SYMBOL\_STRING \] でシンボル SYMBOL\_STRING の値を出力します。|  
|\[\!  loop \]|次の 2 つの方法で使用できます。<br /><br /> -   \[\!  loop \= 5 \]<br />-   \[\!  loop \= *NUM\_OF\_PAGES* \] *NUM\_OF\_PAGES* は数値を持つシンボルです。|  
|\[\!  endloop \]|ループ構造を終了します。|  
  
 感嘆符 \(\!\) の直後の左角かっこ \(\[\) は、テンプレート ディレクティブの開始を示します。  右角かっこは、テンプレート ディレクティブの終わりを示します。  次の構文に従って使用する必要があります。  
  
```  
[!directive params]  
```  
  
 *directive* と  *params* 間には識別子以外の文字または空白を指定する必要があります。  
  
## 例  
  
```  
[!if SAMPLE_RADIO_OPTION1]  
You have checked the option 'Sample radio button option 1'  
[!else]  
You have checked the option 'Sample radio button option 2'  
[!endif]  
```  
  
 テンプレート ファイルでは、上のディレクティブと共に次の演算子を使用できます。  
  
```  
+  
-     
=  
!=     
==     
||     
&&    
!  
```  
  
## 例  
  
```  
[!if SYMBOL_STRING != 0]  
```  
  
## 参照  
 [ウィザード用に作成されるファイル](../ide/files-created-for-your-wizard.md)   
 [カスタム ウィザード](../ide/custom-wizard.md)   
 [カスタム ウィザードの作成](../ide/creating-a-custom-wizard.md)   
 [ウィザードのデザイン](../ide/designing-a-wizard.md)