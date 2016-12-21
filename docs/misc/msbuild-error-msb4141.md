---
title: "MSBuild エラー MSB4141 | Microsoft Docs"
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
  - "MSB4141"
ms.assetid: 0d190884-e64d-4d6b-817d-ce4644788fce
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# MSBuild エラー MSB4141
**MSB4141: ToolsVersion "\<x.x\>" に MSBuildToolsPath が指定されていません。**  
  
 カスタム ツールセットは定義されていますが、`MSBuildToolsPath` に値が指定されていません。  
  
### このエラーを解決するには  
  
-   レジストリまたは [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] 構成ファイルでカスタム ツールセットを定義するときに、`MSBuildToolsPath` に有効な値を指定してください。  
  
## 参照  
 [標準ツールセット構成とカスタム ツールセット構成](../Topic/Standard%20and%20Custom%20Toolset%20Configurations.md)   
 [Project Element \(MSBuild\)](../Topic/Project%20Element%20\(MSBuild\).md)   
 [追加のリソース](../Topic/Additional%20MSBuild%20Resources.md)