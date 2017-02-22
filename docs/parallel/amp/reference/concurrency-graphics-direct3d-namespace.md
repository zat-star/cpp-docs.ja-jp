---
title: "Concurrency::graphics::direct3d 名前空間 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "amp_graphics/Concurrency::graphics::direct3d"
  - "amp_short_vectors/Concurrency::graphics::direct3d"
dev_langs: 
  - "C++"
ms.assetid: be283331-07cf-46e4-91a1-e8aa85d4ec8e
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# Concurrency::graphics::direct3d 名前空間
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

[get\_texture](../Topic/get_texture%20Function.md) メソッドと [make\_texture](../Topic/make_texture%20Function.md) メソッドを提供します。  
  
## 構文  
  
```  
namespace direct3d;  
```  
  
## メンバー  
  
### 関数  
  
|名前|説明|  
|--------|--------|  
|[get\_sampler 関数](../Topic/get_sampler%20Function.md)|指定されたサンプラー オブジェクトを表す特定のアクセラレータ ビューについて、Direct3D サンプラーの状態インターフェイスを取得します。|  
|[get\_texture 関数](../Topic/get_texture%20Function.md)|指定された [texture](../Topic/texture%20Class.md) オブジェクトの基になる Direct3D テクスチャ インターフェイスを取得します。|  
|[make\_sampler 関数](../Topic/make_sampler%20Function.md)|Direct3D サンプラーの状態インターフェイス ポインターからサンプラーを作成します。|  
|[make\_texture 関数](../Topic/make_texture%20Function.md)|指定されたパラメーターを使用して [texture](../Topic/texture%20Class.md) オブジェクトを作成します。|  
|[msad4 関数](../Topic/msad4%20Function.md)|4 バイトの参照値と 8 バイトのソース値を比較し、4 個の合計値のベクターを累積します。|  
  
## 必要条件  
 **ヘッダー:** amp\_graphics.h  
  
 **名前空間:** Concurrency::graphics  
  
## 参照  
 [Concurrency::graphics 名前空間](../../../parallel/amp/reference/concurrency-graphics-namespace.md)