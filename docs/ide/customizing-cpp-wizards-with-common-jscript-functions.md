---
title: "共通の JScript 関数による C++ ウィザードのカスタマイズ | Microsoft Docs"
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
helpviewer_keywords: 
  - "ウィザード JScript メソッド, 作成 (C++ ウィザードを)"
ms.assetid: c602978f-a2c4-462f-85c3-50b5897bec46
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 共通の JScript 関数による C++ ウィザードのカスタマイズ
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[カスタム ウィザード](../ide/creating-a-custom-wizard.md)を備えたウィザード プロジェクトを作成する場合、Common.js が含まれます。  ウィザードに対してユーザー インターフェイスを指定すると、プロジェクトはさらに、次のように JScript スクリプト言語を指定し、Common.js ファイルをインクルードする HTML ページを含みます。  
  
```  
<SCRIPT ID="INCLUDE_COMMON" LANGUAGE ="JSCRIPT"></SCRIPT>  
```  
  
 ウィザードではさらに、Default.js という固有のファイルが作成されます。  Default.js で JScript 関数をカスタマイズできます。  詳細については、「[JScript ファイル](../ide/jscript-file.md)」を参照してください。  
  
 Common.js には、各ウィザードの HTML ページや Default.js から呼び出すことができる関数が含まれています。  複数のウィザードで同じ関数を使用する場合は、その関数を Common.js に追加できます。  
  
## 参照  
 [C\+\+ ウィザードの JScript 関数](../ide/jscript-functions-for-cpp-wizards.md)   
 [カスタム ウィザードの作成](../ide/creating-a-custom-wizard.md)   
 [ウィザードのデザイン](../ide/designing-a-wizard.md)