---
title: "CAtlModuleT クラス | Microsoft Docs"
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
  - "ATL::CAtlModuleT<T>"
  - "ATL.CAtlModuleT"
  - "ATL.CAtlModuleT<T>"
  - "ATL::CAtlModuleT"
  - "CAtlModuleT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAtlModuleT クラス"
ms.assetid: 9b74d02f-9117-47b1-a05e-c5945f83dd2b
caps.latest.revision: 19
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CAtlModuleT クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスは、ATL モジュールを実装します。  
  
## 構文  
  
```  
  
      template <  
   class T   
>   
class ATL_NO_VTABLE CAtlModuleT :  
   public CAtlModule  
```  
  
#### パラメーター  
 `T`  
 `CAtlModuleT`から派生したクラス。  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CAtlModuleT::CAtlModuleT](../Topic/CAtlModuleT::CAtlModuleT.md)|コンストラクターです。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CAtlModuleT::InitLibId](../Topic/CAtlModuleT::InitLibId.md)|現在のモジュールの GUID を含むデータ メンバーを初期化します。|  
|[CAtlModuleT::RegisterAppId](../Topic/CAtlModuleT::RegisterAppId.md)|レジストリに EXE を追加します。|  
|[CAtlModuleT::RegisterServer](../Topic/CAtlModuleT::RegisterServer.md)|レジストリに追加します。|  
|[CAtlModuleT::UnregisterAppId](../Topic/CAtlModuleT::UnregisterAppId.md)|EXE をレジストリから削除します。|  
|[CAtlModuleT::UnregisterServer](../Topic/CAtlModuleT::UnregisterServer.md)|レジストリからサービスを削除します。|  
|[CAtlModuleT::UpdateRegistryAppId](../Topic/CAtlModuleT::UpdateRegistryAppId.md)|レジストリの EXE ファイルの情報を更新します。|  
  
## 解説  
 [CAtlModule](../../atl/reference/catlmodule-class.md)から派生した`CAtlModuleT`は、実行可能ファイル \(EXE\) またはサービス \(EXE\) の ATL モジュールを実装します。  実行可能モジュールはモジュールが Windows サービス アプリケーションのバックグラウンドで実行時に Windows の起動は、ローカル、アウトプロセス サーバーです。  
  
 `CAtlModuleT` は、モジュールの初期化、登録、および登録解除をサポートします。  
  
## 継承階層  
 [\_ATL\_MODULE](../Topic/_ATL_MODULE.md)  
  
 [CAtlModule](../../atl/reference/catlmodule-class.md)  
  
 `CAtlModuleT`  
  
## 必要条件  
 **ヘッダー:** atlbase.h  
  
## 参照  
 [CAtlModule クラス](../../atl/reference/catlmodule-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)   
 [モジュール クラス](../Topic/ATL%20Module%20Classes.md)