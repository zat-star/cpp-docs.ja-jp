---
title: "CWinTraitsOR クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CWinTraitsOR"
  - "ATL::CWinTraitsOR"
  - "CWinTraitsOR"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CWinTraitsOR クラス"
  - "ウィンドウ スタイル, 既定値 (ATL の)"
ms.assetid: 1eb7b1e8-a9bd-411b-a30a-35a8a10af989
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CWinTraitsOR クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスには、ウィンドウ オブジェクトの作成に使用する、スタイルを標準化するためのメソッドが用意されています。  
  
> [!IMPORTANT]
>  このクラスおよびメンバーは、Windows のランタイムで実行するアプリケーションで使用することはできません。  
  
## 構文  
  
```  
  
      template <  
DWORD t_dwStyle= 0,  
DWORDt_dwExStyle= 0,  
class TWinTraits = CControlWinTraits   
>  
class CWinTraitsOR  
```  
  
#### パラメーター  
 `t_dwStyle`  
 既定のウィンドウ スタイル。  
  
 `t_dwExStyle`  
 既定の拡張ウィンドウ スタイル。  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CWinTraitsOR::GetWndExStyle](../Topic/CWinTraitsOR::GetWndExStyle.md)|`CWinTraitsOR` のオブジェクトの拡張スタイルを取得します。|  
|[CWinTraitsOR::GetWndStyle](../Topic/CWinTraitsOR::GetWndStyle.md)|`CWinTraitsOR` のオブジェクトの標準スタイルを取得します。|  
  
## 解説  
 [ウィンドウの特性](../../atl/understanding-window-traits.md) のこのクラスは、ATL ウィンドウ オブジェクトの作成に使用するスタイルを標準化するための簡単な方法を提供します。  このウィンドウ クラスのインスタンスに使用する標準および拡張スタイルの最小セットを指定するに [CWindowImpl](../Topic/CWindowImpl%20Class.md) にテンプレート パラメーターまたは ATL ウィンドウ クラスの一つとしてこのクラスの特殊化を使用します。  
  
 [CWindowImpl::Create](../Topic/CWindowImpl::Create.md)の呼び出しのインスタンスごとに設定する他のスタイルの中に特定のスタイルは、ウィンドウ クラスのすべてのインスタンスに設定されていることを確認するには、テンプレートの特化を使用します。  
  
 他のスタイルが `CWindowImpl::Create`への呼び出しで指定されていない場合にのみ使用される既定のウィンドウ スタイルを指定するには、[CWinTraits](../../atl/reference/cwintraits-class.md) を使用します。  
  
## 必要条件  
 **Header:** atlwin.h  
  
## 参照  
 [クラスの概要](../../atl/atl-class-overview.md)   
 [ウィンドウの特徴について](../../atl/understanding-window-traits.md)