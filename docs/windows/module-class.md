---
title: "Module クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::Module"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Module クラス"
ms.assetid: dd67e3b8-c2e1-4f53-8c0f-565a140ba649
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Module クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

関連オブジェクトのコレクションを表します。  
  
## 構文  
  
```  
  
template<  
   ModuleType moduleType  
>  
class Module;  
  
template<>  
class Module<InProc> : public Details::ModuleBase;  
  
template<>  
class Module<OutOfProc> : public Module<InProc>;  
```  
  
#### パラメーター  
 `moduleType`  
 [ModuleType](../Topic/ModuleType%20Enumeration.md) の一つ以上の列挙値の組み合わせ。  
  
## メンバー  
  
### 保護されたなクラス  
  
|名前|説明|  
|--------|--------|  
|[Module::GenericReleaseNotifier クラス](../windows/module-genericreleasenotifier-class.md)|現在のモジュールの最後のオブジェクトが解放されると、イベント ハンドラーが呼び出されます。  イベント ハンドラーは、ラムダ ファンクタ、または関数へのポインターで指定されます。|  
|[Module::MethodReleaseNotifier クラス](../Topic/Module::MethodReleaseNotifier%20Class.md)|現在のモジュールの最後のオブジェクトが解放されると、イベント ハンドラーが呼び出されます。  イベント ハンドラーは、オブジェクトやポインターにメソッドのメンバーによって指定されます。|  
|[Module::ReleaseNotifier クラス](../Topic/Module::ReleaseNotifier%20Class.md)|モジュールの最後のオブジェクトが解放されると、イベント ハンドラーが呼び出されます。|  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[Module::~Module デストラクター](../windows/module-tilde-module-destructor.md)|Deinitializes モジュール クラスの現在のインスタンス。|  
  
### プロテクト コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[Module::Module コンストラクター](../windows/module-module-constructor.md)|モジュール クラスの新しいインスタンスを初期化します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[Module::Create メソッド](../windows/module-create-method.md)|モジュールのインスタンスを作成します。|  
|[Module::DecrementObjectCount メソッド](../windows/module-decrementobjectcount-method.md)|モジュールで追跡されるオブジェクトの数をデクリメントします。|  
|[Module::GetActivationFactory メソッド](../windows/module-getactivationfactory-method.md)|モジュールのアクティベーション ファクトリを取得します。|  
|[Module::GetClassObject メソッド](../windows/module-getclassobject-method.md)|Retreives クラス ファクトリがキャッシュされます。|  
|[Module::GetModule メソッド](../Topic/Module::GetModule%20Method.md)|モジュールのインスタンスを作成します。|  
|[Module::GetObjectCount メソッド](../windows/module-getobjectcount-method.md)|このモジュールによって管理されるオブジェクトの数を取得します。|  
|[Module::IncrementObjectCount メソッド](../windows/module-incrementobjectcount-method.md)|モジュールで追跡されるオブジェクトの数をインクリメントします。|  
|[Module::RegisterCOMObject メソッド](../windows/module-registercomobject-method.md)|一つ以上の COM オブジェクトを登録して、ほかのアプリケーションでは、に接続できます。|  
|[Module::RegisterObjects メソッド](../windows/module-registerobjects-method.md)|レジスタまたは [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] COM オブジェクトは、ほかのアプリケーションでは、に接続できます。|  
|[Module::RegisterWinRTObject メソッド](../windows/module-registerwinrtobject-method.md)|[!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] の一つ以上のオブジェクトを登録して、ほかのアプリケーションでは、に接続できます。|  
|[Module::Terminate メソッド](../windows/module-terminate-method.md)|シャットダウンするモジュールでインスタンス化されるすべてのファクトリを実現します。|  
|[Module::UnregisterCOMObject メソッド](../Topic/Module::UnregisterCOMObject%20Method.md)|一つ以上の COM オブジェクトを登録解除されますが、他のアプリケーションは、接続することを防止できます。|  
|[Module::UnregisterObjects メソッド](../windows/module-unregisterobjects-method.md)|他のアプリケーションがユーザーに接続できないように指定したモジュールのオブジェクトの登録を解除します。|  
|[Module::UnregisterWinRTObject メソッド](../windows/module-unregisterwinrtobject-method.md)|他のアプリケーションがユーザーに接続できないように [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] の一つ以上のオブジェクトの登録を解除します。|  
  
### プロテクト メソッド  
  
|名前|説明|  
|--------|--------|  
|[Module::Create メソッド](../windows/module-create-method.md)|モジュールのインスタンスを作成します。|  
  
### プロテクト データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[Module::objectCount\_ データ メンバー](../windows/module-objectcount-data-member.md)|どれほど多くのクラスが [作成](../windows/make-function.md) 関数で作成されたかを追跡します。|  
|[Module::releaseNotifier\_ データ メンバー](../windows/module-releasenotifier-data-member.md)|ReleaseNotifier オブジェクトへのポインターを保持します。|  
  
### \[マクロ\]  
  
|||  
|-|-|  
|[ActivatableClass](../Topic/ActivatableClass%20Macros.md)|指定されたクラスのインスタンスを作成するファクトリを含む内部キャッシュを設定します。  このマクロは、既定のファクトリとグループ ID パラメーターを指定します。|  
|[ActivatableClassWithFactory](../Topic/ActivatableClass%20Macros.md)|指定されたクラスのインスタンスを作成するファクトリを含む内部キャッシュを設定します。  このマクロは、特定のファクトリ パラメーターを指定することができます。|  
|[ActivatableClassWithFactoryEx](../Topic/ActivatableClass%20Macros.md)|指定されたクラスのインスタンスを作成するファクトリを含む内部キャッシュを設定します。  このマクロは、特定のファクトリとグループ ID パラメーターを指定することができます。|  
  
## 継承階層  
 `ModuleBase`  
  
 `Module`  
  
 `Module`  
  
## 必要条件  
 **ヘッダー:** module.h  
  
 **名前空間:** Microsoft::WRL  
  
## 参照  
 [Microsoft::WRL 名前空間](../windows/microsoft-wrl-namespace.md)