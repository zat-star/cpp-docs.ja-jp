---
title: "Concurrency::graphics::direct3d Namespace |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- amp_graphics/Concurrency::graphics::direct3d
- amp_short_vectors/Concurrency::graphics::direct3d
dev_langs:
- C++
ms.assetid: be283331-07cf-46e4-91a1-e8aa85d4ec8e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 420a022412d5f66855f834d574f627fdbf7273fd
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="concurrencygraphicsdirect3d-namespace"></a>Concurrency::graphics::direct3d 名前空間
提供、 [get_texture](concurrency-graphics-direct3d-namespace-functions.md#get_texture)と[make_texture](concurrency-graphics-direct3d-namespace-functions.md#make_texture)メソッドです。  
  
## <a name="syntax"></a>構文  
  
```  
namespace direct3d;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="functions"></a>関数  
  
|名前<br /><br /> 説明|  
|--------------------------|  
|[get_sampler](concurrency-graphics-direct3d-namespace-functions.md#get_sampler)<br /><br /> 指定されたサンプラー オブジェクトを表す特定のアクセラレータ ビューについて、Direct3D サンプラーの状態インターフェイスを取得します。|  
|[get_texture](concurrency-graphics-direct3d-namespace-functions.md#get_texture)<br /><br /> 指定した基になる Direct3D テクスチャ インターフェイスを取得[テクスチャ](texture-class.md)オブジェクト。|  
|[make_sampler](concurrency-graphics-direct3d-namespace-functions.md#make_sampler)<br /><br /> Direct3D サンプラーの状態インターフェイス ポインターからサンプラーを作成します。|  
|[make_texture](concurrency-graphics-direct3d-namespace-functions.md#make_texture)<br /><br /> 作成、[テクスチャ](texture-class.md)指定されたパラメーターを使用してオブジェクト。|  
|[msad4](concurrency-graphics-direct3d-namespace-functions.md#msad4)<br /><br /> 4 バイトの参照値と 8 バイトのソース値を比較し、4 個の合計値のベクターを累積します。|  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** amp_graphics.h  
  
 **Namespace:** concurrency::graphics  
  
## <a name="see-also"></a>参照  
 [Concurrency::graphics 名前空間](concurrency-graphics-namespace.md)
