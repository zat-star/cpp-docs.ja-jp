---
title: "コマンド ラインの警告 D9041 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "D9041"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "D9041"
ms.assetid: ada8815f-4246-4e25-b57d-a7f16fa107cc
caps.latest.revision: 3
caps.handback.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コマンド ラインの警告 D9041
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'value' は '\/option' に対して無効な値です。'value' を仮定します。この警告を指定するときは、'\/analyze' をコマンドライン オプションに追加してください  
  
 コード分析の警告番号が **\/wd**、**\/we**、**\/wo**、**\/wl** のいずれかのコマンド ライン オプションに追加されているにもかかわらず、**\/analyze** コマンド ライン オプションが指定されていません。  このエラーを解決するには、**\/analyze** コマンド ライン オプションを追加するか、該当する **\/w** コマンド ライン オプションから無効な警告番号を削除します。  
  
## 使用例  
 次のコマンド ラインの例では、警告 D9041 が生成されます。  
  
```  
cl /EHsc /LD /wd6001 filename.cpp  
```  
  
 この警告を解決するには、**\/analyze** コマンド ライン オプションを追加します。  使用しているバージョンのコンパイラで **\/analyze** がサポートされていない場合は、無効な警告番号を **\/wd** オプションから削除します。  
  
## 参照  
 [コマンド ライン エラー D8000 から D9999](../../error-messages/tool-errors/command-line-errors-d8000-through-d9999.md)   
 [コンパイラ オプション](../../build/reference/compiler-options.md)