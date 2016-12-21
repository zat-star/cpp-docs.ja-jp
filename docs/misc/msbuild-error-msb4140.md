---
title: "MSBuild エラー MSB4140 | Microsoft Docs"
ms.custom: ""
ms.date: "11/24/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "MSB4140"
ms.assetid: 13546558-4ed4-44c2-89a6-f69a2b43ed07
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# MSBuild エラー MSB4140
**MSB4140: 既定のツール バージョンがレジストリにも構成ファイルにも指定されていません。**  
  
 プロジェクトに `ToolsVersion` の既定値が指定されていません。  そのため、[!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] が使用する値を特定できません。  
  
### このエラーを解決するには  
  
-   ツールセットが定義されているレジストリまたは構成ファイル \(msbuild.exe.config など\) に `DefaultToolsVersion` 値が指定されていることを確認してください。  
  
## 参照  
 [標準ツールセット構成とカスタム ツールセット構成](../Topic/Standard%20and%20Custom%20Toolset%20Configurations.md)   
 [Project Element \(MSBuild\)](../Topic/Project%20Element%20\(MSBuild\).md)   
 [追加のリソース](../Topic/Additional%20MSBuild%20Resources.md)