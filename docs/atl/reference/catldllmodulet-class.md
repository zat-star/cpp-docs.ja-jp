---
title: "CAtlDllModuleT クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CAtlDllModuleT"
  - "ATL::CAtlDllModuleT<T>"
  - "ATL::CAtlDllModuleT"
  - "ATL.CAtlDllModuleT<T>"
  - "CAtlDllModuleT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAtlDllModuleT クラス"
ms.assetid: 351d5767-8257-4878-94be-45a85e31a72d
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CAtlDllModuleT クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスは、DLL 用のモジュールを表します。  
  
## 構文  
  
```  
  
      template <  
   class T   
>  
class ATL_NO_VTABLE CAtlDllModuleT :  
   public CAtlModuleT< T >  
```  
  
#### パラメーター  
 `T`  
 `CAtlDllModuleT`から派生したクラス。  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CAtlDllModuleT::CAtlDllModuleT](../Topic/CAtlDllModuleT::CAtlDllModuleT.md)|コンストラクターです。|  
|[CAtlDllModuleT::~CAtlDllModuleT](../Topic/CAtlDllModuleT::~CAtlDllModuleT.md)|デストラクターです。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CAtlDllModuleT::DllCanUnloadNow](../Topic/CAtlDllModuleT::DllCanUnloadNow.md)|DLL がアンロードできるテスト。|  
|[CAtlDllModuleT::DllGetClassObject](../Topic/CAtlDllModuleT::DllGetClassObject.md)|クラス ファクトリを返します。|  
|[CAtlDllModuleT::DllMain](../Topic/CAtlDllModuleT::DllMain.md)|ダイナミック リンク ライブラリ \(DLL\) へのオプションのエントリ ポイント。|  
|[CAtlDllModuleT::DllRegisterServer](../Topic/CAtlDllModuleT::DllRegisterServer.md)|DLL のオブジェクトのシステムのレジストリにエントリを追加します。|  
|[CAtlDllModuleT::DllUnregisterServer](../Topic/CAtlDllModuleT::DllUnregisterServer.md)|DLL のオブジェクトのシステムのレジストリ エントリを削除します。|  
|[CAtlDllModuleT::GetClassObject](../Topic/CAtlDllModuleT::GetClassObject.md)|クラス ファクトリを返します。  [DllGetClassObject](../Topic/CAtlDllModuleT::DllGetClassObject.md)で開始されます。|  
  
## 解説  
 `CAtlDllModuleT` はダイナミック リンク ライブラリ \(DLL\) のモジュールを表し、すべての DLL プロジェクトによって使用される関数を提供します。  [CAtlModuleT](../../atl/reference/catlmodulet-class.md) このクラスの特殊化は登録がサポートされています。  
  
 ATL モジュールの詳細については、[ATL モジュール クラス](../Topic/ATL%20Module%20Classes.md)を参照してください。  
  
## 継承階層  
 [\_ATL\_MODULE](../Topic/_ATL_MODULE.md)  
  
 [CAtlModule](../../atl/reference/catlmodule-class.md)  
  
 [CAtlModuleT](../../atl/reference/catlmodulet-class.md)  
  
 `CAtlDllModuleT`  
  
## 必要条件  
 atlbase.h**Header:**  
  
## 参照  
 [CAtlModuleT クラス](../../atl/reference/catlmodulet-class.md)   
 [CAtlExeModuleT クラス](../../atl/reference/catlexemodulet-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)   
 [モジュール クラス](../Topic/ATL%20Module%20Classes.md)