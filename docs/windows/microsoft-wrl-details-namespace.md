---
title: "Microsoft::WRL::Details 名前空間 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
ms.assetid: d71fe149-d804-4c6f-961d-43fe21ef8630
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Microsoft::WRL::Details 名前空間
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。  
  
## <a name="syntax"></a>構文  
  
```  
namespace Microsoft::WRL::Details;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="classes"></a>クラス  
  
|名前|説明|  
|----------|-----------------|  
|[ComPtrRef クラス](../Topic/ComPtrRef%20Class.md)|ComPtr の型のオブジェクトへの参照を表す \< T>します。|  
|[ComPtrRefBase クラス](../windows/comptrrefbase-class.md)|基本クラスを表す、 [ComPtrRef](../Topic/ComPtrRef%20Class.md) クラスです。|  
|[DontUseNewUseMake クラス](../windows/dontusenewusemake-class.md)|演算子を使用できないように `new` で `RuntimeClass`します。 したがって、使用する必要があります、 [関数](../windows/make-function.md) 代わりにします。|  
|[EventTargetArray クラス](../windows/eventtargetarray-class.md)|イベント ハンドラーの配列を表します。|  
|[MakeAllocator クラス](../windows/makeallocator-class.md)|弱い参照のサポートの有無のアクティブ化可能なクラスのメモリを割り当てます。|  
|[ModuleBase クラス](../windows/modulebase-class.md)|基本クラスを表す、 [モジュール](../windows/module-class.md) クラスです。|  
|[RemoveIUnknown クラス](../windows/removeiunknown-class.md)|等価の型を作成、 `IUnknown`-に基づいて型が、非仮想 `QueryInterface`, 、`AddRef`, 、および `Release` メソッドです。|  
|[WeakReference クラス](../windows/weakreference-class1.md)|表す、 *弱参照* Windows ランタイムまたは従来の COM で使用できます。 弱い参照は、アクセスできる場合とできない場合があるオブジェクトを表します。|  
  
### <a name="structures"></a>構造体  
  
|名前|説明|  
|----------|-----------------|  
|[ArgTraits 構造体](../windows/argtraits-structure.md)|インターフェイスおよびを指定した数のパラメーターを持つ匿名のメンバー関数は、指定したデリゲートを宣言します。|  
|[ArgTraitsHelper 構造体](../windows/argtraitshelper-structure.md)|デリゲート引数の共通の特徴を定義に役立ちます。|  
|[BoolStruct 構造体](../windows/boolstruct-structure.md)|おけば、ComPtr がインターフェイスのオブジェクトの有効期間を管理するかどうかを定義します。 BoolStruct がによって内部的に使用される、 [BoolType()](../windows/comptr-operator-microsoft-wrl-details-booltype-operator.md) 演算子。|  
|[CreatorMap 構造体](../windows/creatormap-structure.md)|初期化、登録、およびオブジェクトの登録を解除する方法についてを説明します。|  
|[DerefHelper 構造体](../Topic/DerefHelper%20Structure.md)|逆参照されるポインターを表す、 `T*` テンプレート パラメーター。|  
|[EnableIf 構造体](../windows/enableif-structure.md)|最初のテンプレート パラメーターと評価された場合、2 番目のテンプレート パラメーターで指定された型のデータ メンバーを定義する `true`です。|  
|[FactoryCache 構造体](../Topic/FactoryCache%20Structure.md)|クラス ファクトリと登録を識別する値の位置を含む [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] または COM クラスのオブジェクト。|  
|[ImplementsBase 構造体](../windows/implementsbase-structure.md)|テンプレート パラメーターの型の検証に使用される [Implements 構造体](../Topic/Implements%20Structure.md)します。|  
|[ImplementsHelper 構造体](../windows/implementshelper-structure.md)|実装を支援、 [実装](../Topic/Implements%20Structure.md) 構造体。|  
|[InterfaceList 構造体](../windows/interfacelist-structure.md)|インターフェイスの再帰的なリストを作成するために使用します。|  
|[InterfaceListHelper 構造体](../Topic/InterfaceListHelper%20Structure.md)|ビルド、 `InterfaceList` 再帰的に指定したテンプレート パラメーターの引数を適用する型。|  
|[InterfaceTraits 構造体](../windows/interfacetraits-structure.md)|インターフェイスの一般的な特徴を実装します。|  
|[InvokeHelper 構造体](../windows/invokehelper-structure.md)|指定した数値と引数の型に基づく Invoke() メソッドの実装を提供します。|  
|[IsBaseOfStrict 構造体](../windows/isbaseofstrict-structure.md)|一方の型がもう一方の型の基本クラスであるかどうかをテストします。|  
|[IsSame 構造体](../windows/issame-structure.md)|テストの種類を指定した 1 つかどうかは、他と同じでは、種類を指定します。|  
|[Nil 構造体](../Topic/Nil%20Structure.md)|指定されていない (省略可能) テンプレート パラメーターを示すために使用します。|  
|[RemoveReference 構造体](../windows/removereference-structure.md)|指定されたクラス テンプレート パラメーターから参照または右辺値参照の特徴を削除します。|  
|[RuntimeClassBase 構造体](../windows/runtimeclassbase-structure.md)|検出するために使用される `RuntimeClass` で、 [ように](../windows/make-function.md) 関数です。|  
|[RuntimeClassBaseT 構造体](../windows/runtimeclassbaset-structure.md)|ヘルパー メソッドを提供 `QueryInterface` 操作とのインターフェイス Id を取得します。|  
|[VerifyInheritanceHelper 構造体](../windows/verifyinheritancehelper-structure.md)|1 つのインターフェイスが別のインターフェイスから派生したかどうかをテストします。|  
|[VerifyInterfaceHelper 構造体](../windows/verifyinterfacehelper-structure.md)|テンプレート パラメーターによって指定されたインターフェイスが特定の要件を満たしていることを確認します。|  
  
### <a name="enumerations"></a>列挙  
  
|名前|説明|  
|----------|-----------------|  
|[AsyncStatusInternal 列挙型](../windows/asyncstatusinternal-enumeration.md)|非同期操作の状態の内部の列挙値の間のマッピングを指定し、 **Windows::Foundation::AsyncStatus** 列挙します。|  
  
### <a name="functions"></a>関数  
  
|名前|説明|  
|----------|-----------------|  
|[ActivationFactoryCallback 関数](../windows/activationfactorycallback-function.md)|指定されたアクティブ化 ID のアクティベーション ファクトリを取得します|  
|[Move 関数](../Topic/Move%20Function.md)|指定された引数を別の場所に移動します。|  
|[RaiseException 関数](../windows/raiseexception-function.md)|呼び出し元のスレッドで例外が発生します。|  
|[Swap 関数 (Windows ランタイム C++ テンプレート ライブラリ)](../windows/swap-function-windows-runtime-cpp-template-library.md)|指定された 2 つの引数の値を交換します。|  
|[TerminateMap 関数](../windows/terminatemap-function.md)|指定したモジュール内のクラス ファクトリを終了します。|  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** async.h、client.h、corewrappers.h、event.h、ftm.h、implements.h、internal.h、module.h  
  
 **名前空間:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>関連項目  
 [Microsoft::wrl 名前空間](../windows/microsoft-wrl-namespace.md)   
 [Microsoft::WRL::Wrappers 名前空間](../Topic/Microsoft::WRL::Wrappers%20Namespace.md)