---
title: "CAtlModule クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CAtlModule"
  - "CAtlModule"
  - "ATL.CAtlModule"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAtlModule クラス"
ms.assetid: 63fe02f1-4c4b-4e7c-ae97-7ad7b4252415
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CAtlModule クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスには、複数の ATL モジュール クラスで使用するメソッドが用意されています。  
  
## 構文  
  
```  
  
   class ATL_NO_VTABLE CAtlModule :  
public _ATL_MODULE  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CAtlModule::CAtlModule](../Topic/CAtlModule::CAtlModule.md)|コンストラクターです。|  
|[CAtlModule::~CAtlModule](../Topic/CAtlModule::~CAtlModule.md)|デストラクターです。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CAtlModule::AddCommonRGSReplacements](../Topic/CAtlModule::AddCommonRGSReplacements.md)|ATL レジストリの構成 \(レジストラー\) 置換マップにパラメーターを追加するには、このメソッドをオーバーライドします。|  
|[CAtlModule::AddTermFunc](../Topic/CAtlModule::AddTermFunc.md)|モジュールが終了したときに呼び出される新しい関数を追加します。|  
|[CAtlModule::GetGITPtr](../Topic/CAtlModule::GetGITPtr.md)|グローバル インターフェイス ポインターを返します。|  
|[CAtlModule::GetLockCount](../Topic/CAtlModule::GetLockCount.md)|ロックの数を返します。|  
|[CAtlModule::Lock](../Topic/CAtlModule::Lock.md)|ロック カウントをインクリメントします。|  
|[CAtlModule::Term](../Topic/CAtlModule::Term.md)|すべてのデータ メンバーを解放します。|  
|[CAtlModule::Unlock](../Topic/CAtlModule::Unlock.md)|ロック カウントをデクリメントします。|  
|[CAtlModule::UpdateRegistryFromResourceD](../Topic/CAtlModule::UpdateRegistryFromResourceD.md)|登録するために指定したリソースを登録または登録解除に含まれるスクリプト オブジェクトを移動します。|  
|[CAtlModule::UpdateRegistryFromResourceDHelper](../Topic/CAtlModule::UpdateRegistryFromResourceDHelper.md)|このメソッドは `UpdateRegistryFromResourceD` で、レジストリの更新を実行するために呼び出されます。|  
|[CAtlModule::UpdateRegistryFromResourceS](../Topic/CAtlModule::UpdateRegistryFromResourceS.md)|登録するために指定したリソースを登録または登録解除に含まれるスクリプト オブジェクトを移動します。  このメソッドは、ATL レジストリ コンポーネントに静的にリンクされます。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CAtlModule::m\_libid](../Topic/CAtlModule::m_libid.md)|現在のモジュールの GUID が含まれます。|  
|[CAtlModule::m\_pGIT](../Topic/CAtlModule::m_pGIT.md)|グローバル インターフェイス テーブルへのポインター。|  
  
## 解説  
 [CAtlDllModuleT のクラス](../../atl/reference/catldllmodulet-class.md)、[CAtlExeModuleT のクラス](../../atl/reference/catlexemodulet-class.md)と [CAtlServiceModuleT のクラス](../Topic/CAtlServiceModuleT%20Class.md) して、このクラスがアプリケーションの DLL、EXE のアプリケーションと Windows サービスをサポートするには、それぞれ使用されます。  
  
 ATL モジュールの詳細については、[ATL モジュール クラス](../Topic/ATL%20Module%20Classes.md)を参照してください。  
  
 このクラスは、ATL の以前のバージョンで使用されている旧式の [CComModule クラス](../../atl/reference/ccommodule-class.md) を置き換えます。  
  
## 継承階層  
 [\_ATL\_MODULE](../Topic/_ATL_MODULE.md)  
  
 `CAtlModule`  
  
## 必要条件  
 **ヘッダー:** atlbase.h  
  
## 参照  
 [\_ATL\_MODULE](../Topic/_ATL_MODULE.md)   
 [クラスの概要](../../atl/atl-class-overview.md)   
 [モジュール クラス](../Topic/ATL%20Module%20Classes.md)   
 [レジストリ コンポーネント \(レジストラー\)](../../atl/atl-registry-component-registrar.md)