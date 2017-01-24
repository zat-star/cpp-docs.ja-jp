---
title: "プロジェクトのスレッド モデルの指定 (ATL) | Microsoft Docs"
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
  - "_ATL_APARTMENT_THREADED マクロ"
  - "_ATL_FREE_THREADED マクロ"
  - "_ATL_SINGLE_THREADED マクロ"
  - "ATL, マルチスレッド"
  - "スレッド処理 [ATL], モデル"
ms.assetid: 6b571078-521c-4f3e-9f08-482aa235a822
caps.latest.revision: 10
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# プロジェクトのスレッド モデルの指定 (ATL)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

次のマクロは、ATL プロジェクトのスレッド処理モデルを指定して用意されています:  
  
|マクロ|使用するガイドライン|  
|---------|----------------|  
|\_ATL\_SINGLE\_THREADED|、のすべてのオブジェクトがシングルスレッド モデルを使用する場合に定義します。|  
|\_ATL\_APARTMENT\_THREADED|1 つ以上のオブジェクトでアパートメント スレッドを使用する場合に定義します。|  
|\_ATL\_FREE\_THREADED|1 つ以上のオブジェクトでフリー スレッドまたはニュートラル スレッドを使用する場合に定義します。  既存のコードは同等のマクロ [\_ATL\_MULTI\_THREADED](../Topic/_ATL_MULTI_THREADED.md)への参照が含まれる場合があります。|  
  
 プロジェクトのこれらのマクロを一つも定義しない場合、\_ATL\_FREE\_THREADED が有効になります。  
  
 マクロは次のようにランタイム パフォーマンスに影響します:  
  
-   プロジェクトのオブジェクトに対応するマクロを指定すると、ランタイム パフォーマンスが向上します。  
  
-   、のすべてのオブジェクトが一つのスレッドとたとえば\_ATL\_APARTMENT\_THREADED を指定するマクロのレベルを指定するには、少し実行時のパフォーマンスが著しく低下します。  
  
-   、一つ以上のオブジェクトでアパートメント スレッドまたはフリーのスレッドを使用する場合\_ATL\_SINGLE\_THREADED を指定するマクロの低レベルを指定すると、実行時に発生してアプリケーションが発生する場合があります。  
  
 ATL オブジェクトで使用可能なスレッド処理モデルの詳細については、[オプション、ATL シンプル オブジェクト ウィザード](../atl/reference/options-atl-simple-object-wizard.md) を参照してください。  
  
## 参照  
 [概念](../atl/active-template-library-atl-concepts.md)