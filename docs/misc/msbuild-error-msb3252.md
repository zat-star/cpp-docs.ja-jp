---
title: "MSBuild エラー MSB3252 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "MSB3252"
helpviewer_keywords: 
  - "MSB3252"
ms.assetid: 4e6982b8-84b3-4d21-94e1-05cc10bf1393
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# MSBuild エラー MSB3252
**MSB3252: アセンブリ \<name\> を解決できませんでした。  このアセンブリは、.NET Framework Client Profile   の一部として一覧表示されていません。**  
  
 [!INCLUDE[net_client_v35_long](../misc/includes/net_client_v35_long_md.md)] に含まれないアセンブリまたは依存アセンブリのメンバーへの呼び出しが行われました。  呼び出しを解決できないため、アプリケーションをコンパイルできません。  
  
 [!INCLUDE[net_client_v35_long](../misc/includes/net_client_v35_long_md.md)] の詳細については、「[.NET Framework Client Profile](../Topic/.NET%20Framework%20Client%20Profile.md)」を参照してください。  
  
### このエラーを解決するには  
  
-   指定されたアセンブリ参照をプロジェクトから削除するか、プロジェクトの対象を、[!INCLUDE[net_client_v35_long](../misc/includes/net_client_v35_long_md.md)] サブセット ライブラリではなく完全な [!INCLUDE[dnprdnshort](../Token/dnprdnshort_md.md)] にします。  完全な [!INCLUDE[dnprdnshort](../Token/dnprdnshort_md.md)] を対象にする方法の詳細については、「[方法: .NET Framework のバージョンをターゲットにする](../Topic/How%20to:%20Target%20a%20Version%20of%20the%20.NET%20Framework.md)」を参照してください。  
  
## 参照  
 [ターゲット フレームワークおよびターゲット プラットフォーム](../Topic/MSBuild%20Target%20Framework%20and%20Target%20Platform.md)   
 [Project Element \(MSBuild\)](../Topic/Project%20Element%20\(MSBuild\).md)   
 [追加のリソース](../Topic/Additional%20MSBuild%20Resources.md)