---
title: "Microsoft::WRL 名前空間 | Microsoft Docs"
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
  - "implements/Microsoft::WRL"
  - "module/Microsoft::WRL"
  - "async/Microsoft::WRL"
  - "internal/Microsoft::WRL"
  - "event/Microsoft::WRL"
  - "ftm/Microsoft::WRL"
  - "client/Microsoft::WRL"
  - "corewrappers/Microsoft::WRL"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "WRL 名前空間"
ms.assetid: 01118a8f-f564-4859-b87e-9444848585a1
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Microsoft::WRL 名前空間
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] を構成する基本型を定義します。  
  
## <a name="syntax"></a>構文  
  
```  
namespace Microsoft::WRL;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="typedefs"></a>Typedef  
  
|名前|説明|  
|----------|-----------------|  
|`InhibitWeakReferencePolicy`|`RuntimeClassFlags<WinRt &#124; InhibitWeakReference>`|  
  
### <a name="classes"></a>クラス  
  
|名前|説明|  
|----------|-----------------|  
|[ActivationFactory クラス](../windows/activationfactory-class.md)|1 つ以上のクラスを Windows ランタイムによってアクティブ化できるようにします。|  
|[AsyncBase クラス](../windows/asyncbase-class.md)|Windows ランタイムの非同期ステート マシンを実装します。|  
|[ClassFactory クラス](../windows/classfactory-class.md)|`IClassFactory` インターフェイスの基本機能を実装します。|  
|[ComPtr クラス](../windows/comptr-class.md)|テンプレート パラメーターで指定されたインターフェイスを表す *スマート ポインター* 型を作成します。 ComPtr は、基になるインターフェイス ポインターの参照カウントを自動的に維持し、参照カウントがゼロになるとそのインターフェイスを解放します。|  
|[DeferrableEventArgs クラス](../windows/deferrableeventargs-class.md)|遅延のイベント引数の型に使用されるテンプレート クラス。|  
|[EventSource クラス](../windows/eventsource-class.md)|イベントを表します。 `EventSource` メンバー関数は、イベント ハンドラーの追加、削除、および呼び出しを実行します。|  
|[FtmBase クラス](../windows/ftmbase-class.md)|フリー スレッド マーシャラー オブジェクトを表します。|  
|[モジュール クラス](../windows/module-class.md)|関連するオブジェクトから成るコレクションを表します。|  
|[RuntimeClass クラス](../windows/runtimeclass-class.md)|指定した数のインターフェイスを継承し、指定した Windows ランタイム、クラシック COM、および弱い参照をサポートする、インスタンス化されたクラスを表します。|  
|[SimpleActivationFactory クラス](../windows/simpleactivationfactory-class.md)|Windows ランタイムまたはクラシック COM の基底クラスを作成するための基本的なメカニズムを提供します。|  
|[SimpleClassFactory クラス](../windows/simpleclassfactory-class.md)|基底クラスを作成するための基本的なメカニズムを提供します。|  
|[WeakRef クラス](../windows/weakref-class.md)|表す、 *弱参照* のみ Windows ランタイムいない従来の COM. で使用できます。 弱い参照は、アクセスできる場合とできない場合があるオブジェクトを表します。|  
  
### <a name="structures"></a>構造体  
  
|名前|説明|  
|----------|-----------------|  
|[ChainInterfaces 構造体](../windows/chaininterfaces-structure.md)|一連のインターフェイス ID に適用できる検証および初期化関数を指定します。|  
|[CloakedIid 構造体](../windows/cloakediid-structure.md)|IID リスト内で指定されたインターフェイスにアクセスできないことを、RuntimeClass、Implements、および ChainInterfaces テンプレートに示します。|  
|[Implements 構造体](../Topic/Implements%20Structure.md)|指定されたインターフェイスの QueryInterface と GetIid を実装します。|  
|[MixIn 構造体](../windows/mixin-structure.md)|ランタイム クラスが Windows ランタイム インターフェイス (存在する場合) から派生し、次にクラシック COM インターフェイスから派生していることを確認します。|  
|[RuntimeClassFlags 構造体](../windows/runtimeclassflags-structure.md)|インスタンスの型を含む、 [RuntimeClass](../windows/runtimeclass-class.md)します。|  
  
### <a name="enumerations"></a>列挙体  
  
|名前|説明|  
|----------|-----------------|  
|[AsyncResultType 列挙型](../windows/asyncresulttype-enumeration.md)|GetResults() メソッドによって返される結果の型を指定します。|  
|[ModuleType 列挙型](../Topic/ModuleType%20Enumeration.md)|モジュールがインプロセス サーバーまたはアウトプロセス サーバーをサポートするかどうかを指定します。|  
|[RuntimeClassType 列挙型](../windows/runtimeclasstype-enumeration.md)|型を指定 [RuntimeClass](../windows/runtimeclass-class.md) サポートされているインスタンス。|  
  
### <a name="functions"></a>関数  
  
|名前|説明|  
|----------|-----------------|  
|[AsWeak 関数](../windows/asweak-function.md)|指定されたインスタンスへの弱い参照を取得します。|  
|[コールバック関数](../windows/callback-function-windows-runtime-cpp-template-library.md)|メンバー関数がコールバック メソッドであるオブジェクトを作成します。|  
|[CreateActivationFactory 関数](../windows/createactivationfactory-function.md)|Windows ランタイムによるアクティブ化が可能な、指定されたクラスのインスタンスを生成するファクトリを作成します。|  
|[CreateClassFactory 関数](../windows/createclassfactory-function.md)|指定されたクラスのインスタンスを生成するファクトリを作成します。|  
|[Make 関数](../windows/make-function.md)|指定された [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] クラスを初期化します。|  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** async.h、client.h、corewrappers.h、event.h、ftm.h、implements.h、internal.h、module.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>「  
 [Microsoft::WRL::Wrappers 名前空間](../Topic/Microsoft::WRL::Wrappers%20Namespace.md)