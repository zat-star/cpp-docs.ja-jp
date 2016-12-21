---
title: "カテゴリ別の主要な WRL API | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
ms.assetid: 7367bacf-6b7c-4ecd-a0ce-a662db46fc66
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# カテゴリ別の主要な WRL API
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

次の表では、一覧プライマリ [!INCLUDE[cppwrl](../windows/includes/cppwrl_md.md)] クラス、構造体、関数、およびマクロです。 ヘルパーの名前空間とクラスの構成要素が省略されています。 これらのリストは、名前空間によって配置された API のドキュメントを強化します。  
  
### <a name="classes"></a>クラス  
  
|タイトル|説明|  
|-----------|-----------------|  
|[ActivationFactory クラス](../windows/activationfactory-class.md)|1 つ以上のクラスを Windows ランタイムによってアクティブ化できるようにします。|  
|[AsyncBase クラス](../windows/asyncbase-class.md)|Windows ランタイムの非同期ステート マシンを実装します。|  
|[ClassFactory クラス](../windows/classfactory-class.md)|`IClassFactory` インターフェイスの基本機能を実装します。|  
|[ComPtr クラス](../windows/comptr-class.md)|テンプレート パラメーターで指定されたインターフェイスを表す *スマート ポインター* 型を作成します。 ComPtr は、基になるインターフェイス ポインターの参照カウントを自動的に維持し、参照カウントがゼロになるとそのインターフェイスを解放します。|  
|[イベント クラス (Windows ランタイム C++ テンプレート ライブラリ)](../windows/event-class-windows-runtime-cpp-template-library.md)|イベントを表します。|  
|[EventSource クラス](../windows/eventsource-class.md)|イベントを表します。 `EventSource` メンバー関数は、イベント ハンドラーの追加、削除、および呼び出しを実行します。|  
|[FtmBase クラス](../windows/ftmbase-class.md)|フリー スレッド マーシャラー オブジェクトを表します。|  
|[HandleT クラス](../Topic/HandleT%20Class.md)|オブジェクトへのハンドルを表します。|  
|[HString クラス](../windows/hstring-class.md)|HSTRING ハンドルの操作をサポートします。|  
|[HStringReference クラス](../windows/hstringreference-class.md)|既存の文字列から作成された HSTRING を表します。|  
|[モジュール クラス](../windows/module-class.md)|関連するオブジェクトから成るコレクションを表します。|  
|[Module::genericreleasenotifier クラス](../windows/module-genericreleasenotifier-class.md)|現在のモジュール内の最後のオブジェクトを解放すると、イベント ハンドラーを呼び出します。 イベント ハンドラーは、ラムダ、ファンクタ、または関数へのポインターによって指定されます。|  
|[Module::methodreleasenotifier クラス](../Topic/Module::MethodReleaseNotifier%20Class.md)|現在のモジュール内の最後のオブジェクトを解放すると、イベント ハンドラーを呼び出します。 イベント ハンドラーには、オブジェクトとそのメソッドへのポインターのメンバーを指定します。|  
|[Module::releasenotifier クラス](../Topic/Module::ReleaseNotifier%20Class.md)|モジュールの最後のオブジェクトがリリースされたときに、イベント ハンドラーを呼び出します。|  
|[RoInitializeWrapper クラス](RoInitializeWrapper%20Class.md)|[!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] を初期化します。|  
|[RuntimeClass クラス](../windows/runtimeclass-class.md)|指定した数のインターフェイスを継承し、指定した Windows ランタイム、クラシック COM、および弱い参照をサポートする、インスタンス化されたクラスを表します。|  
|[SimpleActivationFactory クラス](../windows/simpleactivationfactory-class.md)|Windows ランタイムまたはクラシック COM の基底クラスを作成するための基本的なメカニズムを提供します。|  
|[SimpleClassFactory クラス](../windows/simpleclassfactory-class.md)|基底クラスを作成するための基本的なメカニズムを提供します。|  
|[WeakRef クラス](../windows/weakref-class.md)|表す、 *弱参照* のみ Windows ランタイムいない従来の COM. で使用できます。 弱い参照は、アクセスできる場合とできない場合があるオブジェクトを表します。|  
  
### <a name="structures"></a>構造体  
  
|タイトル|説明|  
|-----------|-----------------|  
|[ChainInterfaces 構造体](../windows/chaininterfaces-structure.md)|一連のインターフェイス ID に適用できる検証および初期化関数を指定します。|  
|[CloakedIid 構造体](../windows/cloakediid-structure.md)|ことを示します、 `RuntimeClass`, 、`Implements` と `ChainInterfaces` テンプレートが、指定したインターフェイスが IID リストでアクセスできることです。|  
|[Implements 構造体](../Topic/Implements%20Structure.md)|実装して `QueryInterface` と `GetIid` の指定されたインターフェイスです。|  
|[MixIn 構造体](../windows/mixin-structure.md)|ランタイム クラスが Windows ランタイム インターフェイス (存在する場合) から派生し、次にクラシック COM インターフェイスから派生していることを確認します。|  
  
### <a name="functions"></a>関数  
  
|タイトル|説明|  
|-----------|-----------------|  
|[ActivateInstance 関数](../windows/activateinstance-function.md)|登録し、指定したクラス ID で定義されている、指定した型のインスタンスを取得|  
|[AsWeak 関数](../windows/asweak-function.md)|指定されたインスタンスへの弱い参照を取得します。|  
|[コールバック関数](../windows/callback-function-windows-runtime-cpp-template-library.md)|メンバー関数がコールバック メソッドであるオブジェクトを作成します。|  
|[CreateActivationFactory 関数](../windows/createactivationfactory-function.md)|Windows ランタイムによるアクティブ化が可能な、指定されたクラスのインスタンスを生成するファクトリを作成します。|  
|[CreateClassFactory 関数](../windows/createclassfactory-function.md)|指定されたクラスのインスタンスを生成するファクトリを作成します。|  
|[GetActivationFactory 関数](../windows/getactivationfactory-function.md)|テンプレート パラメーターで指定された型のアクティベーション ファクトリを取得します。|  
|[Make 関数](../windows/make-function.md)|指定された [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] クラスを初期化します。|  
  
### <a name="macros"></a>[マクロ]  
  
|タイトル|説明|  
|-----------|-----------------|  
|[ActivatableClass マクロ](../Topic/ActivatableClass%20Macros.md)|指定したクラスのインスタンスを作成できるファクトリを含む内部キャッシュを設定します。|  
|[InspectableClass マクロ](../windows/inspectableclass-macro.md)|ランタイム クラス名と信頼レベルを設定します。|  
  
## <a name="see-also"></a>関連項目  
 [Windows ランタイム C++ テンプレート ライブラリ (WRL)](../Topic/Windows%20Runtime%20C++%20Template%20Library%20\(WRL\).md)