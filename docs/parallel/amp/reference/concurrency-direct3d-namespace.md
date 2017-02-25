---
title: "Concurrency::direct3d 名前空間 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "amp/Concurrency::direct3d"
  - "amprt/Concurrency::direct3d"
  - "amp_short_vectors/Concurrency::direct3d"
  - "amp_graphics/Concurrency::direct3d"
  - "amp_math/Concurrency::direct3d"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "direct3d 名前空間"
ms.assetid: 9566a2f1-4d5f-43e4-a3ac-676643d38420
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 15
---
# Concurrency::direct3d 名前空間
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

`direct3d` 名前空間は、D3D の相互運用性をサポートする関数を提供します。  これにより、AMP コードでの計算に D3D のリソースをシームレスに使用できるようになると共に、AMP で作成したリソースを D3D コードで使用することができ、冗長な中間コピーを作成する必要がありません。  C\+\+ AMP を使用することによって、DirectX アプリケーションの計算中心のセクションの処理を加速し、AMP の計算から生成されるデータに対して D3D API を使用できます。  
  
## 構文  
  
```  
namespace direct3d;  
```  
  
## メンバー  
  
### クラス  
  
|名前|説明|  
|--------|--------|  
|[scoped\_d3d\_access\_lock クラス](../Topic/scoped_d3d_access_lock%20Class.md)|`accelerator_view` オブジェクトの D3D アクセスのロックの RAII ラッパー。|  
  
### 構造体  
  
|名前|説明|  
|--------|--------|  
|[adopt\_d3d\_access\_lock\_t 構造体](../../../parallel/amp/reference/adopt-d3d-access-lock-t-structure.md)|D3D のアクセスのロックを示すタグの種類は、取得するのではなく、導入する必要があります。|  
  
### 関数  
  
|名前|説明|  
|--------|--------|  
|[abs 関数](../Topic/abs%20Function.md)|引数の絶対値を返します。|  
|[clamp 関数](../Topic/clamp%20Function.md)|オーバーロードされます。  \_X を指定された \_Min と \_Max の範囲にクランプします。|  
|[countbits 関数](../Topic/countbits%20Function.md)|\_X 内で設定されているビットの数をカウントします。|  
|[create\_accelerator\_view 関数](../Topic/create_accelerator_view%20Function.md)|Direct3D デバイス インターフェイスへのポインターから [accelerator\_view クラス](../Topic/accelerator_view%20Class.md) を作成します。|  
|[d3d\_access\_lock 関数](../Topic/d3d_access_lock%20Function.md)|accelerator\_view と共有されるリソースに対して安全に D3D 演算を実行する目的で、accelerator\_view のロックを取得します。|  
|[d3d\_access\_try\_lock 関数](../Topic/d3d_access_try_lock%20Function.md)|ブロックせずに、accelerator\_view に対する D3D アクセスのロックを取得します。|  
|[d3d\_access\_unlock 関数](../Topic/d3d_access_unlock%20Function.md)|指定された accelerator\_view に対する D3D アクセスのロックを解除します。|  
|[firstbithigh 関数](../Topic/firstbithigh%20Function.md)|最上位ビットから下位に向かって操作して、\_X 内で最初に設定されているビットの位置を取得します。|  
|[firstbitlow 関数](../Topic/firstbitlow%20Function.md)|最下位ビットから上位に向かって操作して、\_X 内で最初に設定されているビットの位置を取得します。|  
|[get\_buffer 関数](../Topic/get_buffer%20Function.md)|配列を基にする D3D バッファー インターフェイスを取得します。|  
|[imax 関数](../Topic/imax%20Function.md)|2 つの値を比較し、大きい方の値を返します。|  
|[imin 関数](../Topic/imin%20Function.md)|2 つの値を比較し、小さい方の値を返します。|  
|[is\_timeout\_disabled 関数](../Topic/is_timeout_disabled%20Function.md)|指定された accelerator\_view についてタイムアウトが無効であるかどうかを示すブール型のフラグを返します。|  
|[mad 関数](../Topic/mad%20Function.md)|オーバーロードされます。  3 個の引数に対して乗算\/加算算術演算 \(\_X \* \_Y \+ \_Z\) を実行します。|  
|[make\_array 関数](../Topic/make_array%20Function.md)|D3D バッファーのインターフェイス ポインターから配列を作成します。|  
|[noise 関数](../Topic/noise%20Function.md)|パーリン ノイズ アルゴリズムを使用して乱数値を生成します。|  
|[radians 関数](../Topic/radians%20Function.md)|\_X を角度からラジアンに変換します。|  
|[rcp 関数](../Topic/rcp%20Function.md)|引数の高速近似逆数を計算します。|  
|[reversebits 関数](../Topic/reversebits%20Function.md)|\_X 内のビットの順序を反転させます。|  
|[saturate 関数](../Topic/saturate%20Function.md)|0 ～ 1 の範囲内で \_X をクランプします。|  
|[sign 関数](../Topic/sign%20Function.md)|オーバーロードされます。  引数の正弦を返します。|  
|[smoothstep 関数](../Topic/smoothstep%20Function.md)|\_X が \[\_Min, \_Max\] の範囲内にある場合、0 ～ 1 の滑らかなエルミート補間を返します。|  
|[step 関数](../Topic/step%20Function.md)|2 つの値を比較し、どちらの値が大きいかに応じて 0 または 1 を返します。|  
|[umax 関数](../Topic/umax%20Function.md)|2 つの符号なしの値を比較し、大きい方の値を返します。|  
|[umin 関数](../Topic/umin%20Function.md)|2 つの符号なしの値を比較し、小さい方の値を返します。|  
  
## 必要条件  
 **ヘッダー:** amp.h  
  
 **名前空間:** Concurrency  
  
## 参照  
 [Concurrency 名前空間 \(C\+\+ AMP\)](../../../parallel/amp/reference/concurrency-namespace-cpp-amp.md)