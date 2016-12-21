---
title: "CAtlAutoThreadModuleT クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CAtlAutoThreadModuleT"
  - "ATL::CAtlAutoThreadModuleT"
  - "CAtlAutoThreadModuleT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAtlAutoThreadModuleT クラス"
ms.assetid: ae1667c6-3fb8-47bc-b35d-9ea5e9896d7f
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CAtlAutoThreadModuleT クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスには、スレッドがプールされているアパートメント モデル COM サーバーを実装するためのメソッドが用意されています。  
  
> [!IMPORTANT]
>  このクラスおよびメンバーは、Windows のランタイムで実行するアプリケーションで使用することはできません。  
  
## 構文  
  
```  
  
      template <  
class T,  
class ThreadAllocator= CComSimpleThreadAllocator,  
DWORD dwWait= INFINITE   
>  
class ATL_NO_VTABLE CAtlAutoThreadModuleT :  
public IAtlAutoThreadModule  
```  
  
#### パラメーター  
 `T`  
 COM サーバーを実装するクラス。  
  
 `ThreadAllocator`  
 クラスのスレッドの選択。  既定値は [CComSimpleThreadAllocator](../../atl/reference/ccomsimplethreadallocator-class.md)です。  
  
 `dwWait`  
 タイムアウト間隔をミリ秒単位で指定します。  つまり、メソッドのタイムアウト間隔は、経過していないことを既定値は型です。  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CAtlAutoThreadModuleT::GetDefaultThreads](../Topic/CAtlAutoThreadModuleT::GetDefaultThreads.md)|この静的関数は、プロセッサの数に基づいて動的に EXE モジュールのスレッドの最大数を計算して返します。|  
  
## 解説  
 クラス [CAtlAutoThreadModule](../../atl/reference/catlautothreadmodule-class.md) は `CAtlAutoThreadModuleT` からスレッドのプールされているアパートメント モデル COM サーバーを実装するために取得します。  これは、旧式のクラス [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md)を置き換えます。  
  
> [!NOTE]
>  このクラスは、DLL 内の DLL がアンロードされると、無限の既定の `dwWait` の値によりデッドロックが発生することになるため、使用しないでください。  
  
## 継承階層  
 `IAtlAutoThreadModule`  
  
 `CAtlAutoThreadModuleT`  
  
## 必要条件  
 **ヘッダー:** atlbase.h  
  
## 参照  
 [IAtlAutoThreadModule クラス](../../atl/reference/iatlautothreadmodule-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)   
 [IAtlAutoThreadModule クラス](../../atl/reference/iatlautothreadmodule-class.md)   
 [モジュール クラス](../Topic/ATL%20Module%20Classes.md)