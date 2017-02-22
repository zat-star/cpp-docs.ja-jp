---
title: "CComModule クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CComModule"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComModule クラス"
  - "DLL モジュール [C++], ATL"
ms.assetid: f5face2c-8fd8-40e6-9ec3-54ab74701769
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# CComModule クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ATL 7.0 では、`CComModule` は使用されなくなりました。詳細については、「[ATL モジュール クラス](../Topic/ATL%20Module%20Classes.md)」を参照してください。  
  
> [!IMPORTANT]
>  このクラスおよびメンバーは、Windows のランタイムで実行するアプリケーションで使用することはできません。  
  
## 構文  
  
```  
class CComModule : public _ATL_MODULE  
```  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CComModule::GetClassObject](../Topic/CComModule::GetClassObject.md)|指定の CLSID を持つオブジェクトを作成します。  DLLs 専用です。|  
|[CComModule::GetModuleInstance](../Topic/CComModule::GetModuleInstance.md)|`m_hInst` を返します。|  
|[CComModule::GetResourceInstance](../Topic/CComModule::GetResourceInstance.md)|`m_hInstResource` を返します。|  
|[CComModule::GetTypeLibInstance](../Topic/CComModule::GetTypeLibInstance.md)|`m_hInstTypeLib` を返します。|  
|[CComModule::Init](../Topic/CComModule::Init.md)|データ メンバーを初期化します。|  
|[CComModule::RegisterClassHelper](../Topic/CComModule::RegisterClassHelper.md)|システム レジストリにオブジェクトの標準クラスの登録を入力します。|  
|[CComModule::RegisterClassObjects](../Topic/CComModule::RegisterClassObjects.md)|クラス オブジェクトを登録します。  EXE だけです。|  
|[CComModule::RegisterServer](../Topic/CComModule::RegisterServer.md)|オブジェクト マップ内の各オブジェクトのシステム レジストリを更新します。|  
|[CComModule::RegisterTypeLib](../Topic/CComModule::RegisterTypeLib.md)|タイプ ライブラリを登録します。|  
|[CComModule::RevokeClassObjects](../Topic/CComModule::RevokeClassObjects.md)|クラス オブジェクトを取り消します。  EXE だけです。|  
|[CComModule::Term](../Topic/CComModule::Term.md)|データ メンバーを解放します。|  
|[CComModule::UnregisterClassHelper](../Topic/CComModule::UnregisterClassHelper.md)|システムのレジストリからオブジェクトの標準クラスの登録を解除します。|  
|[CComModule::UnregisterServer](../Topic/CComModule::UnregisterServer.md)|オブジェクト マップ内の各オブジェクトを登録解除します。|  
|[CComModule::UpdateRegistryClass](../Topic/CComModule::UpdateRegistryClass.md)|レジスタまたはアンバインド オブジェクトの標準クラスの登録。|  
|[CComModule::UpdateRegistryFromResourceD](../Topic/CComModule::UpdateRegistryFromResourceD.md)|登録するために指定したリソースを登録または登録解除に含まれるスクリプト オブジェクトを移動します。|  
|[CComModule::UpdateRegistryFromResourceS](../Topic/CComModule::UpdateRegistryFromResourceS.md)|ATL レジストリ コンポーネントに静的にリンクします。  登録するために指定したリソースを登録または登録解除に含まれるスクリプト オブジェクトを移動します。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CComModule::m\_csObjMap](../Topic/CComModule::m_csObjMap.md)|ensures オブジェクト マップ情報へのアクセスを実行します。|  
|[CComModule::m\_csTypeInfoHolder](../Topic/CComModule::m_csTypeInfoHolder.md)|ensures タイプ ライブラリ情報へのアクセスを実行します。|  
|[CComModule::m\_csWindowCreate](../Topic/CComModule::m_csWindowCreate.md)|ensures ウィンドウの作成時に使用されるウィンドウ クラス情報と静的データへのアクセスを実行します。|  
|[CComModule::m\_hInst](../Topic/CComModule::m_hInst.md)|モジュールのインスタンスへのハンドルが含まれます。|  
|[CComModule::m\_hInstResource](../Topic/CComModule::m_hInstResource.md)|既定では、モジュールのインスタンスへのハンドルが含まれます。|  
|[CComModule::m\_hInstTypeLib](../Topic/CComModule::m_hInstTypeLib.md)|既定では、モジュールのインスタンスへのハンドルが含まれます。|  
|[CComModule::m\_pObjMap](../Topic/CComModule::m_pObjMap.md)|モジュールで保持されるオブジェクト マップをポイントし例に反映されます。|  
  
## 解説  
  
> [!NOTE]
>  このクラスは使用されなくなりました。現在の ATL のコード生成ウィザードでは、[CAtlAutoThreadModule](../../atl/reference/catlautothreadmodule-class.md) および [CAtlModule](../../atl/reference/catlmodule-class.md) の派生クラスが使用されます。  詳細については、「[ATL モジュール クラス](../Topic/ATL%20Module%20Classes.md)」を参照してください。  ATL の旧リリースで作成されたアプリケーションのために、以下に説明を示します。  `CComModule` は、下位互換性のために ATL の一部として残されています。  
  
 `CComModule` は、COM サーバー モジュールを実装して、クライアントがモジュールのコンポーネントにアクセスできるようにします。  `CComModule` は、DLL \(インプロセス\) モジュールと EXE \(ローカル\) モジュールの両方をサポートします。  
  
 `CComModule` インスタンスは、オブジェクト マップを使用して、一連のクラス オブジェクト定義を保持します。  このオブジェクト マップは、`_ATL_OBJMAP_ENTRY` 構造体の配列として実装され、次の情報を格納します。  
  
-   レジストリ内のオブジェクト記述の入力および削除に関する情報  
  
-   クラス ファクトリを通じたオブジェクトのインスタンス化に関する情報  
  
-   クライアントとコンポーネントのルート オブジェクトとの間に確立する通信リンクに関する情報  
  
-   クラス オブジェクトの有効期間の管理に関する情報  
  
 ATL COM AppWizard を実行すると、`_Module` が自動的に生成されます。これは、`CComModule` またはその派生クラスのグローバル インスタンスです。  ATL プロジェクト ウィザードの詳細については、「[ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)」を参照してください。  
  
 `CComModule` のほかにも、ATL には、EXE と Windows サービスのためのアパートメント モデルのモジュールを実装する [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md) が用意されています。  複数のアパートメントにオブジェクトを作成するときは、`CComAutoThreadModule` からモジュールを派生します。  
  
## 継承階層  
 [\_ATL\_MODULE](../Topic/_ATL_MODULE.md)  
  
 [CAtlModule](../../atl/reference/catlmodule-class.md)  
  
 [CAtlModuleT](../../atl/reference/catlmodulet-class.md)  
  
 `CComModule`  
  
## 必要条件  
 `Header:` atlbase.h  
  
## 参照  
 [クラスの概要](../../atl/atl-class-overview.md)