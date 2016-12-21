---
title: "レジストラー コードへの静的リンクのセットアップ (C++ のみ) | Microsoft Docs"
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
  - "リンク [C++], to ATL Registrar code"
  - "静的リンク (ATL レジスタ コードに)"
ms.assetid: 835f5885-87a6-48fa-91e6-60988ee65538
caps.latest.revision: 11
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# レジストラー コードへの静的リンクのセットアップ (C++ のみ)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

C\+\+ クライアントはレジストラー コードに静的リンクを作成できます。  レジストラー パーサーの静的リンクはリリース ビルドに約 5K を追加します。  
  
 静的リンクを設定する最も簡単な方法は、オブジェクトの宣言で [DECLARE\_REGISTRY\_RESOURCEID](../Topic/DECLARE_REGISTRY_RESOURCEID.md) を指定したとします。  \(これは、ATL で使用される既定の仕様です\)。  
  
### 静的リンクを DECLARE\_REGISTRY\_RESOURCEID を使用して作成するには  
  
1.  \/D**\_ATL\_DLL**の代わりに [\/D](../build/reference/d-preprocessor-definitions.md)`_ATL_STATIC_REGISTRY` を指定します。  
  
2.  再コンパイルします。  
  
## 参照  
 [レジストリ コンポーネント \(レジストラー\)](../atl/atl-registry-component-registrar.md)