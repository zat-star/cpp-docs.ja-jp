---
title: "オプション、ATL プロパティ ページ ウィザード | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "vc.codewiz.class.atl.ppg.options"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL プロパティ ページ ウィザード、オプション"
ms.assetid: a7107779-b2ea-4f99-b84b-7f3e0c504bc8
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# オプション、ATL プロパティ ページ ウィザード
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ウィザードのこのページを使用して、作成するプロパティ ページのスレッド モデルと集約レベルを定義します。  
  
 **スレッド モデル**  
 プロパティ ページで使用するスレッド モデルを指定します。  
  
 詳細については、「[プロジェクトのスレッド モデルの指定](../../atl/specifying-the-threading-model-for-a-project-atl.md)」を参照してください。  
  
|オプション|説明|  
|-----------|--------|  
|`Single`|プロパティ ページは、プライマリ COM スレッドだけで実行されます。|  
|**\[アパートメント\]**|プロパティ ページは、任意のシングル スレッド アパートメントで作成できます。  既定値です。|  
  
 **\[集約\]**  
 作成するプロパティ ページに集約サポートを追加します。  詳細については、「[アグリゲーション](../../atl/aggregation.md)」を参照してください。  
  
|オプション|説明|  
|-----------|--------|  
|**はい**|集約できるプロパティ ページが作成されます。|  
|**いいえ**|集約できないプロパティ ページが作成されます。|  
|**\[アグリゲーションのみ\]**|集約を通じてのみインスタンス化されるプロパティ ページが作成されます。|  
  
## 参照  
 [ATL プロパティ ページ ウィザード](../../atl/reference/atl-property-page-wizard.md)   
 [文字列、ATL プロパティ ページ ウィザード](../../atl/reference/strings-atl-property-page-wizard.md)