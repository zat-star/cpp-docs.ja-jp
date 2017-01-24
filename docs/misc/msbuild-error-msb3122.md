---
title: "MSBuild エラー MSB3122 | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "GenerateManifest.FileAssociationsApplicationNotFullTrust"
helpviewer_keywords: 
  - "MSB3122"
ms.assetid: 523e4160-f165-437a-9f19-fb2ec77d46f5
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# MSBuild エラー MSB3122
**MSB3122: ファイルの関連付けを使用するには、完全な信頼が必要です。**  
  
 ファイルの関連付けを構成するアプリケーションを発行する場合、アプリケーションが完全信頼アプリケーションであることが必要です。  
  
### このエラーを解決するには  
  
-   ClickOnce セキュリティ設定を有効にし、アプリケーションを完全信頼アプリケーションに設定します。  詳細については、「[方法 : ClickOnce のセキュリティ設定を有効にする](../Topic/How%20to:%20Enable%20ClickOnce%20Security%20Settings.md)」を参照してください。  
  
## 参照  
 [\[発行\] ページ \(プロジェクト デザイナー\)](../Topic/Publish%20Page,%20Project%20Designer.md)   
 [ClickOnce アプリケーション マニフェスト](../Topic/ClickOnce%20Application%20Manifest.md)   
 [ClickOnce アプリケーションのコード アクセス セキュリティ](../Topic/Code%20Access%20Security%20for%20ClickOnce%20Applications.md)