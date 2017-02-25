---
title: "ATL Classes | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "index-page "
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL, クラス"
  - "クラス [C++], ATL"
ms.assetid: 7da42e2d-ac84-4506-92bd-502a86d68bdc
caps.latest.revision: 26
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 29
---
# ATL Classes
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Active Template Library \(ATL\) には次の各クラスがあります。  カテゴリ別にクラスを探すには、「[ATL クラスの概要](../../atl/atl-class-overview.md)」を参照してください。  
  
|Class|説明|ヘッダー ファイル|  
|-----------|--------|---------------|  
|[CA2AEX](../../atl/reference/ca2aex-class.md)|このクラスは、文字列変換マクロ `CA2TEX` と `CT2AEX`、および typedef **CA2A** で使用されます。|atlconv.h|  
|[CA2CAEX](../../atl/reference/ca2caex-class.md)|このクラスは、文字列変換マクロ `CA2CTEX` と `CT2CAEX`、および typedef **CA2CA** で使用されます。|atlconv.h|  
|[CA2WEX](../../atl/reference/ca2wex-class.md)|このクラスは、文字列変換マクロ `CA2TEX`、`CA2CTEX`、`CT2WEX`、`CT2CWEX`、および typedef **CA2W** で使用されます。|atlconv.h|  
|[~CAccessToken](../Topic/CAccessToken%20Class.md)|このクラスは、アクセス トークンのラッパー クラスです。|atlsecurity.h|  
|[CAcl](../../atl/reference/cacl-class.md)|このクラスは、アクセス制御リスト \(ACL: Access Control List\) 構造体のラッパー クラスです。|atlsecurity.h|  
|[CAdapt](../../atl/reference/cadapt-class.md)|このテンプレートは、オブジェクトのアドレス以外の値を返すために、アドレス演算子を再定義するクラスをラップするときに使用されます。|atlcomcli.h|  
|[CAtlArray](../../atl/reference/catlarray-class.md)|このクラスは、配列オブジェクトを実装します。|atlcoll.h|  
|[CAtlAutoThreadModule](../../atl/reference/catlautothreadmodule-class.md)|このクラスは、スレッドがプールされているアパートメント モデル COM サーバーを実装します。|atlbase.h|  
|[CAtlAutoThreadModuleT](../../atl/reference/catlautothreadmodulet-class.md)|このクラスには、スレッドがプールされているアパートメント モデル COM サーバーを実装するためのメソッドが用意されています。|atlbase.h|  
|[CAtlBaseModule](../Topic/CAtlBaseModule%20Class.md)|このクラスは、すべての ATL プロジェクトでインスタンス化されます。|atlcore.h|  
|[CAtlComModule](../../atl/reference/catlcommodule-class.md)|このクラスは、COM サーバー モジュールを実装します。|atlbase.h|  
|[CAtlDebugInterfacesModule](../../atl/reference/catldebuginterfacesmodule-class.md)|このクラスは、デバッグ インターフェイスをサポートします。|atlbase.h|  
|[CAtlDllModuleT](../../atl/reference/catldllmodulet-class.md)|このクラスは、DLL 用のモジュールを表します。|atlbase.h|  
|[CAtlException](../Topic/CAtlException%20Class.md)|このクラスは、ATL の例外を定義します。|atlexcept.h|  
|[CAtlExeModuleT](../../atl/reference/catlexemodulet-class.md)|このクラスは、アプリケーション用のモジュールを表します。|atlbase.h|  
|[CAtlFile](../../atl/reference/catlfile-class.md)|このクラスは、Windows のファイル処理 API の Thin ラッパーを提供します。|atlfile.h|  
|[CAtlFileMapping](../Topic/CAtlFileMapping%20Class.md)|このクラスは、[CAtlFileMappingBase](../../atl/reference/catlfilemappingbase-class.md) のメソッドにキャスト演算子を追加し、メモリ マップト ファイルを表します。|atlfile.h|  
|[CAtlFileMappingBase](../../atl/reference/catlfilemappingbase-class.md)|このクラスは、メモリ マップト ファイルを表します。|atlfile.h|  
|[CAtlList](../Topic/CAtlList%20Class.md)|このクラスには、リスト オブジェクトを作成および管理するためのメソッドが用意されています。|atlcoll.h|  
|[CAtlMap](../../atl/reference/catlmap-class.md)|このクラスには、マップ オブジェクトを作成および管理するためのメソッドが用意されています。|atlcoll.h|  
|[CAtlModule](../../atl/reference/catlmodule-class.md)|このクラスには、複数の ATL モジュール クラスで使用するメソッドが用意されています。|atlbase.h|  
|[CAtlModuleT](../../atl/reference/catlmodulet-class.md)|このクラスは、ATL モジュールを実装します。|atlbase.h|  
|[CAtlPreviewCtrlImpl](../../atl/reference/catlpreviewctrlimpl-class.md)|このクラスは、リッチ プレビュー用にシェルが用意するホスト ウィンドウに配置されるウィンドウの ATL 実装です。|atlpreviewctrlimpl.h|  
|[CAtlServiceModuleT](../Topic/CAtlServiceModuleT%20Class.md)|このクラスは、サービスを実装します。|atlbase.h|  
|[CAtlTemporaryFile](../../atl/reference/catltemporaryfile-class.md)|このクラスには、一時ファイルを作成および使用するためのメソッドが用意されています。|atlfile.h|  
|[CAtlTransactionManager](../../atl/reference/catltransactionmanager-class.md)|このクラスは、カーネル トランザクション マネージャー \(KTM: Kernel Transaction Manager\) 関数のラッパーを提供します。|atltransactionmanager.h|  
|[CAtlWinModule](../../atl/reference/catlwinmodule-class.md)|このクラスは、ATL ウィンドウ処理コンポーネントをサポートします。|atlbase.h|  
|[CAutoPtr](../../atl/reference/cautoptr-class.md)|このクラスは、スマート ポインター オブジェクトを表します。|atlbase.h|  
|[CAutoPtrArray](../../atl/reference/cautoptrarray-class.md)|このクラスには、スマート ポインターの配列を構築するときに役立つメソッドが用意されています。|atlbase.h|  
|[CAutoPtrElementTraits](../Topic/CAutoPtrElementTraits%20Class.md)|このクラスには、スマート ポインターのコレクションを作成するときに役立つメソッド、静的関数、および typedef が用意されています。|atlcoll.h|  
|[CAutoPtrList](../../atl/reference/cautoptrlist-class.md)|このクラスには、スマート ポインターのリストを構築するときに役立つメソッドが用意されています。|atlcoll.h|  
|[CAutoVectorPtr](../../atl/reference/cautovectorptr-class.md)|このクラスは、ベクターの new 演算子と delete 演算子を使用して、スマート ポインター オブジェクトを表します。|atlbase.h|  
|[CAutoVectorPtrElementTraits](../../atl/reference/cautovectorptrelementtraits-class.md)|このクラスには、ベクターの new 演算子と delete 演算子を使用してスマート ポインターのコレクションを作成するときに役立つメソッド、静的関数、および typedef が用意されています。|atlcoll.h|  
|[CAxDialogImpl](../Topic/CAxDialogImpl%20Class.md)|このクラスは、ActiveX コントロールをホストするダイアログ ボックス \(モーダルまたはモードレス\) を実装します。|atlwin.h|  
|[CAxWindow](../../atl/reference/caxwindow-class.md)|このクラスには、ActiveX コントロールをホストするウィンドウを操作するためのメソッドが用意されています。|atlwin.h|  
|[CAxWindow2T](../Topic/CAxWindow2T%20Class.md)|このクラスには、ActiveX コントロールおよびライセンスされた ActiveX コントロールをホストするウィンドウを操作するためのメソッドが用意されています。|atlwin.h|  
|[CBindStatusCallback](../Topic/CBindStatusCallback%20Class.md)|このクラスは、`IBindStatusCallback` インターフェイスを実装します。|atlctl.h|  
|[CComAggObject](../../atl/reference/ccomaggobject-class.md)|このクラスは、集約されるオブジェクトの [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) を実装します。|atlcom.h|  
|[CComAllocator](../../atl/reference/ccomallocator-class.md)|このクラスには、COM メモリ ルーチンを使用したメモリ管理用のメソッドが用意されています。|atlbase.h|  
|[CComApartment](../../atl/reference/ccomapartment-class.md)|このクラスは、スレッドがプールされている EXE モジュールにおけるアパートメントの管理をサポートします。|atlbase.h|  
|[CComAutoCriticalSection](../../atl/reference/ccomautocriticalsection-class.md)|このクラスには、クリティカル セクション オブジェクトの所有権を取得および解放するためのメソッドが用意されています。|atlcore.h|  
|[CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md)|ATL 7.0 では、`CComAutoThreadModule` が互換性のために残されています。詳細については、「[ATL モジュール クラス](../Topic/ATL%20Module%20Classes.md)」を参照してください。|atlbase.h|  
|[CComBSTR](../../atl/reference/ccombstr-class.md)|このクラスは、`BSTR` のラッパー クラスです。|atlbase.h|  
|[CComCachedTearOffObject](../../atl/reference/ccomcachedtearoffobject-class.md)|このクラスは、ティアオフ インターフェイスの [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) を実装します。|atlcom.h|  
|[CComClassFactory](../../atl/reference/ccomclassfactory-class.md)|このクラスは、[IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364) インターフェイスを実装します。|atlcom.h|  
|[CComClassFactory2](../Topic/CComClassFactory2%20Class.md)|このクラスは、[IClassFactory2](http://msdn.microsoft.com/library/windows/desktop/ms692720) インターフェイスを実装します。|atlcom.h|  
|[CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md)|このクラスは、[IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364) インターフェイスを実装し、複数のアパートメントでのオブジェクトの作成を許可します。|atlcom.h|  
|[CComClassFactorySingleton](../../atl/reference/ccomclassfactorysingleton-class.md)|このクラスは、[CComClassFactory](../../atl/reference/ccomclassfactory-class.md) から派生します。また、[CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) を使用して単一のオブジェクトを生成します。|atlcom.h|  
|[CComCoClass](../Topic/CComCoClass%20Class.md)|このクラスには、クラスのインスタンスを作成し、そのプロパティを取得するためのメソッドが用意されています。|atlcom.h|  
|[CComCompositeControl](../../atl/reference/ccomcompositecontrol-class.md)|このクラスには、複合コントロールの実装に必要なメソッドが用意されています。|atlctl.h|  
|[CComContainedObject](../../atl/reference/ccomcontainedobject-class.md)|このクラスは、オーナー オブジェクトの **IUnknown** に処理を任せることによって、[IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) を実装します。|atlcom.h|  
|[CComControl](../../atl/reference/ccomcontrol-class.md)|このクラスには、ATL コントロールを作成および管理するためのメソッドが用意されています。|atlctl.h|  
|[CComControlBase](../Topic/CComControlBase%20Class.md)|このクラスには、ATL コントロールを作成および管理するためのメソッドが用意されています。|atlctl.h|  
|[CComCriticalSection](../Topic/CComCriticalSection%20Class.md)|このクラスには、クリティカル セクション オブジェクトの所有権を取得および解放するためのメソッドが用意されています。|atlcore.h|  
|[CComCritSecLock](../../atl/reference/ccomcritseclock-class.md)|このクラスには、クリティカル セクション オブジェクトをロックおよびロック解除するためのメソッドが用意されています。|atlbase.h|  
|[CComCurrency](../../atl/reference/ccomcurrency-class.md)|このクラスには、`CURRENCY` オブジェクトを作成および管理するためのメソッドと演算子が用意されています。|atlcur.h|  
|[CComDynamicUnkArray](../Topic/CComDynamicUnkArray%20Class.md)|このクラスは、**IUnknown** ポインターの配列を格納します。|atlcom.h|  
|[CComEnum](../../atl/reference/ccomenum-class.md)|このクラスは、配列に基づいた COM 列挙子オブジェクトを定義します。|atlcom.h|  
|[CComEnumImpl](../../atl/reference/ccomenumimpl-class.md)|このクラスは、COM 列挙子インターフェイスの実装を提供します。このインターフェイスでは、列挙されるアイテムが配列に格納されます。|atlcom.h|  
|[CComEnumOnSTL](../../atl/reference/ccomenumonstl-class.md)|このクラスは、STL コレクションに基づいた COM 列挙子オブジェクトを定義します。|atlcom.h|  
|[CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md)|このクラスには [CComCriticalSection](../Topic/CComCriticalSection%20Class.md) と同じメソッドが用意されていますが、クリティカル セクションは用意されていません。|atlcore.h|  
|[CComGITPtr](../Topic/CComGITPtr%20Class.md)|このクラスには、インターフェイス ポインターおよびグローバル インターフェイス テーブル \(GIT: Global Interface Table\) を扱うメソッドが用意されています。|atlbase.h|  
|[CComHeap](../../atl/reference/ccomheap-class.md)|このクラスは、COM メモリ割り当て関数を使用して、[IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) を実装します。|ATLComMem.h|  
|[CComHeapPtr](../../atl/reference/ccomheapptr-class.md)|ヒープ ポインターを管理するためのスマート ポインター クラスです。|atlbase.h|  
|[CComModule](../../atl/reference/ccommodule-class.md)|ATL 7.0 では、`CComModule` が互換性のために残されています。詳細については、「[ATL モジュール クラス](../Topic/ATL%20Module%20Classes.md)」を参照してください。|atlbase.h|  
|[CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md)|このクラスには、変数の値をインクリメントおよびデクリメントするためのスレッドセーフなメソッドが用意されています。|atlbase.h|  
|[CComMultiThreadModelNoCS](../Topic/CComMultiThreadModelNoCS%20Class.md)|このクラスには、変数の値をインクリメントおよびデクリメントするためのスレッドセーフなメソッドが用意されています。ただし、クリティカル セクションのロック機能またはロックの解除機能はありません。|atlbase.h|  
|[CComObject](../../atl/reference/ccomobject-class.md)|このクラスは、非集約オブジェクトの **IUnknown** を実装します。|atlcom.h|  
|[CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md)|このクラスは、`Base` オブジェクトを含むモジュールの参照カウントを管理します。|atlcom.h|  
|[CComObjectNoLock](../Topic/CComObjectNoLock%20Class.md)|このクラスは非集約オブジェクトの **IUnknown** を実装しますが、コンストラクターではモジュールのロック カウントがインクリメントされません。|atlcom.h|  
|[CComObjectRoot](../../atl/reference/ccomobjectroot-class.md)|[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md) のこの typedef は、サーバーの既定のスレッド化モデルでテンプレート化されます。|atlcom.h|  
|[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)|このクラスには、非集約オブジェクトと集約オブジェクトの両方について、オブジェクトの参照カウントを管理するメソッドが用意されています。|atlcom.h|  
|[CComObjectStack](../Topic/CComObjectStack%20Class.md)|このクラスは、一時的な COM オブジェクトを作成し、そのオブジェクトに **IUnknown** のスケルトン実装を提供します。|atlcom.h|  
|[CComPolyObject](../../atl/reference/ccompolyobject-class.md)|このクラスは、集約オブジェクトまたは非集約オブジェクトの **IUnknown** を実装します。|atlcom.h|  
|[CComPtr](../../atl/reference/ccomptr-class.md)|COM インターフェイス ポインターを管理するためのスマート ポインター クラスです。|atlcomcli.h|  
|[CComPtrBase](../../atl/reference/ccomptrbase-class.md)|このクラスは、COM ベースのメモリ ルーチンを使用するスマート ポインター クラスの基本クラスとなります。|atlcomcli.h|  
|[CComQIPtr](../../atl/reference/ccomqiptr-class.md)|COM インターフェイス ポインターを管理するためのスマート ポインター クラスです。|atlcomcli.h|  
|[CComQIPtrElementTraits](../Topic/CComQIPtrElementTraits%20Class.md)|このクラスには、COM インターフェイス ポインターのコレクションを作成するときに役立つメソッド、静的関数、および typedef が用意されています。|atlcoll.h|  
|[CComSafeArray](../Topic/CComSafeArray%20Class.md)|このクラスは、`SAFEARRAY Data Type` 構造体のラッパー クラスです。|atlsafe.h|  
|[CComSafeArrayBound](../../atl/reference/ccomsafearraybound-class.md)|このクラスは、`SAFEARRAYBOUND` 構造体のラッパー クラスです。|atlsafe.h|  
|[CComSimpleThreadAllocator](../../atl/reference/ccomsimplethreadallocator-class.md)|このクラスは、[CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md) クラスのスレッドの選択を管理します。|atlbase.h|  
|[CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md)|このクラスには、変数の値をインクリメントおよびデクリメントするための各種メソッドが用意されています。|atlbase.h|  
|[CComTearOffObject](../../atl/reference/ccomtearoffobject-class.md)|このクラスは、ティアオフ インターフェイスを実装します。|atlcom.h|  
|[CComUnkArray](../../atl/reference/ccomunkarray-class.md)|このクラスは、**IUnknown** ポインターを格納し、[IConnectionPointImpl](../Topic/IConnectionPointImpl%20Class.md) テンプレート クラスのパラメーターとして使用されるようにデザインされています。|atlcom.h|  
|[CComVariant](../../atl/reference/ccomvariant-class.md)|このクラスは VARIANT 型をラップします。このクラスには、格納されたデータの型を示すメンバーが用意されています。|atlcomcli.h|  
|[CContainedWindowT](../Topic/CContainedWindowT%20Class.md)|このクラスは、別のオブジェクトに含まれているウィンドウを実装します。|atlwin.h|  
|[CCRTAllocator](../../atl/reference/ccrtallocator-class.md)|このクラスには、CRT メモリ ルーチンを使用するメモリ管理用のメソッドが用意されています。|atlcore.h|  
|[CCRTHeap](../../atl/reference/ccrtheap-class.md)|このクラスは、CRT ヒープ関数を使用して、[IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) を実装します。|atlmem.h|  
|[CDacl](../../atl/reference/cdacl-class.md)|このクラスは、随意アクセス制御リスト \(DACL: Discretionary Access\-control List\) 構造体のラッパー クラスです。|atlsecurity.h|  
|[CDebugReportHook クラス](../../atl/reference/cdebugreporthook-class.md)|このクラスは、名前付きパイプにデバッグ レポートを送信するために使用します。|atlutil.h|  
|[CDefaultCharTraits](../../atl/reference/cdefaultchartraits-class.md)|このクラスには、大文字と小文字を変換するための 2 つの静的関数が用意されています。|atlcoll.h|  
|[CDefaultCompareTraits](../../atl/reference/cdefaultcomparetraits-class.md)|このクラスには、既定の要素比較関数が用意されています。|atlcoll.h|  
|[CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)|このクラスには、コレクション クラス用の既定のメソッドと関数が用意されています。|atlcoll.h|  
|[CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md)|このクラスには、ハッシュ値を計算するための静的関数が用意されています。|atlcoll.h|  
|[CDialogImpl](../Topic/CDialogImpl%20Class.md)|このクラスには、モーダル ダイアログ ボックスまたはモードレス ダイアログ ボックスを作成するためのメソッドが用意されています。|atlwin.h|  
|[CDynamicChain](../../atl/reference/cdynamicchain-class.md)|このクラスには、メッセージ マップの動的チェインをサポートするメソッドが用意されています。|atlwin.h|  
|[CElementTraits](../../atl/reference/celementtraits-class.md)|このクラスは、移動、コピー、比較、ハッシュの各操作のメソッドと関数を提供するために、コレクション クラスによって使用されます。|atlcoll.h|  
|[CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)|このクラスには、コレクション クラス用の既定のコピー メソッドと移動メソッドが用意されています。|atlcoll.h|  
|[CFirePropNotifyEvent](../Topic/CFirePropNotifyEvent%20Class.md)|このクラスには、コントロール プロパティの変更についてコンテナーのシンクに通知するためのメソッドが用意されています。|atlctl.h|  
|[CGlobalHeap](../../atl/reference/cglobalheap-class.md)|このクラスは、Win32 グローバル ヒープ関数を使用して、[IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) を実装します。|atlmem.h|  
|[CHandle](../../atl/reference/chandle-class.md)|このクラスには、ハンドル オブジェクトを作成および使用するためのメソッドが用意されています。|atlbase.h|  
|[CHeapPtr](../../atl/reference/cheapptr-class.md)|ヒープ ポインターを管理するためのスマート ポインター クラスです。|atlcore.h|  
|[CHeapPtrBase](../../atl/reference/cheapptrbase-class.md)|このクラスは、スマート ヒープ ポインター クラスの基本クラスとなります。|atlcore.h|  
|[CHeapPtrElementTraits クラス](../../atl/reference/cheapptrelementtraits-class.md)|このクラスには、ヒープ ポインターのコレクションを作成するときに役立つメソッド、静的関数、および typedef が用意されています。|atlcoll.h|  
|[CHeapPtrList](../../atl/reference/cheapptrlist-class.md)|このクラスには、ヒープ ポインターのリストを構築するときに役立つメソッドが用意されています。|atlcoll.h|  
|[CImage](../../atl-mfc-shared/reference/cimage-class.md)|ビットマップの拡張サポートを提供するクラスです。たとえば、JPEG、GIF、BMP、PNG \(Portable Network Graphics\) 形式のイメージの読み込みや保存などができます。|atlimage.h|  
|[CInterfaceArray](../../atl/reference/cinterfacearray-class.md)|このクラスには、COM インターフェイス ポインターの配列を構築するときに役立つメソッドが用意されています。|atlcoll.h|  
|[CInterfaceList](../Topic/CInterfaceList%20Class.md)|このクラスには、COM インターフェイス ポインターのリストを構築するときに役立つメソッドが用意されています。|atlcoll.h|  
|[CLocalHeap](../../atl/reference/clocalheap-class.md)|このクラスは、Win32 ローカル ヒープ関数を使用して、[IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) を実装します。|atlmem.h|  
|[CMessageMap](../../atl/reference/cmessagemap-class.md)|このクラスでは、オブジェクトのメッセージ マップに別のオブジェクトからアクセスできます。|atlwin.h|  
|[CNonStatelessWorker クラス](../Topic/CNonStatelessWorker%20Class.md)|スレッド プールからの要求を受け取り、ワーカー オブジェクトに渡します。ワーカー オブジェクトは、要求のたびに作成および破棄されます。|atlutil.h|  
|[CNoWorkerThread クラス](../../atl/reference/cnoworkerthread-class.md)|このクラスは、動的キャッシュ管理を無効にする場合に、`MonitorClass` テンプレート パラメーターのキャッシュ クラスの引数として使用します。|atlutil.h|  
|[CPathT クラス](../../atl/reference/cpatht-class.md)|このクラスはパスを表します。|atlpath.h|  
|[CPrimitiveElementTraits](../../atl/reference/cprimitiveelementtraits-class.md)|このクラスには、プリミティブ型で構成されたコレクション クラス用の既定のメソッドと関数が用意されています。|atlcoll.h|  
|[CPrivateObjectSecurityDesc](../Topic/CPrivateObjectSecurityDesc%20Class.md)|このクラスは、プライベート オブジェクトのセキュリティ記述子オブジェクトを表します。|atlsecurity.h|  
|[CRBMap](../../atl/reference/crbmap-class.md)|このクラスは、レッドブラック バイナリ ツリーを使用して、マップ構造体を表します。|atlcoll.h|  
|[CRBMultiMap](../../atl/reference/crbmultimap-class.md)|このクラスは、レッドブラック バイナリ ツリーを使用して、各キーを複数の値に関連付けることができるマップ構造体を表します。|atlcoll.h|  
|[CRBTree](../../atl/reference/crbtree-class.md)|このクラスには、レッドブラック ツリーを作成および利用するためのメソッドが用意されています。|atlcoll.h|  
|[CRegKey](../../atl/reference/cregkey-class.md)|このクラスには、システム レジストリ内のエントリを操作するためのメソッドが用意されています。|atlbase.h|  
|[CRTThreadTraits](../Topic/CRTThreadTraits%20Class.md)|このクラスには、CRT スレッド用の作成関数が用意されています。  スレッドが CRT 関数を使用する場合に、このクラスを使用します。|atlbase.h|  
|[CSacl](../Topic/CSacl%20Class.md)|このクラスは、システム アクセス制御リスト \(SACL: System Access\-Control List\) 構造体のラッパー クラスです。|atlsecurity.h|  
|[CSecurityAttributes](../../atl/reference/csecurityattributes-class.md)|このクラスは、**SECURITY\_ATTRIBUTES** 構造体の Thin ラッパーです。|atlsecurity.h|  
|[CSecurityDesc](../../atl/reference/csecuritydesc-class.md)|このクラスは、**SECURITY\_DESCRIPTOR** 構造体のラッパー クラスです。|atlsecurity.h|  
|[CSid](../../atl/reference/csid-class.md)|このクラスは、`SID` \(セキュリティ識別子\) 構造体のラッパー クラスです。|atlsecurity.h|  
|[CSimpleArray](../../atl/reference/csimplearray-class.md)|このクラスには、単純な配列を管理するためのメソッドが用意されています。|atlsimpcoll.h|  
|[CSimpleArrayEqualHelper](../../atl/reference/csimplearrayequalhelper-class.md)|このクラスは、[CSimpleArray](../../atl/reference/csimplearray-class.md) クラスのヘルパーです。|atlsimpcoll.h|  
|[CSimpleArrayEqualHelperFalse](../Topic/CSimpleArrayEqualHelperFalse%20Class.md)|このクラスは、[CSimpleArray](../../atl/reference/csimplearray-class.md) クラスのヘルパーです。|atlsimpcoll.h|  
|[CSimpleDialog](../../atl/reference/csimpledialog-class.md)|このクラスは、基本的なモーダル ダイアログ ボックスを実装します。|atlwin.h|  
|[CSimpleMap](../../atl/reference/csimplemap-class.md)|このクラスは、単純なマップ配列をサポートします。|atlsimpcoll.h|  
|[CSimpleMapEqualHelper](../../atl/reference/csimplemapequalhelper-class.md)|このクラスは、[CSimpleMap](../../atl/reference/csimplemap-class.md) クラスのヘルパーです。|atlsimpcoll.h|  
|[CSimpleMapEqualHelperFalse](../../atl/reference/csimplemapequalhelperfalse-class.md)|このクラスは、[CSimpleMap](../../atl/reference/csimplemap-class.md) クラスのヘルパーです。|atlsimpcoll.h|  
|[CSnapInItemImpl](../../atl/reference/csnapinitemimpl-class.md)|このクラスには、スナップイン ノード オブジェクトを実装するためのメソッドが用意されています。|atlsnap.h|  
|[CSnapInPropertyPageImpl](../../atl/reference/csnapinpropertypageimpl-class.md)|このクラスには、スナップイン プロパティ ページ オブジェクトを実装するためのメソッドが用意されています。|atlsnap.h|  
|[CStockPropImpl](../../atl/reference/cstockpropimpl-class.md)|このクラスには、ストック プロパティ値をサポートするためのメソッドが用意されています。|atlctl.h|  
|[CStringElementTraits](../../atl/reference/cstringelementtraits-class.md)|このクラスには、`CString` オブジェクトを格納するコレクション クラスで使用する静的関数が用意されています。|cstringt.h|  
|[CStringElementTraitsI](../../atl/reference/cstringelementtraitsi-class.md)|このクラスには、コレクション クラス オブジェクトに格納されている文字列に関連する静的関数が用意されています。  [CStringElementTraits](../../atl/reference/cstringelementtraits-class.md) と似ていますが、大文字と小文字を区別せずに比較を行います。|atlcoll.h|  
|[CStringRefElementTraits](../../atl/reference/cstringrefelementtraits-class.md)|このクラスには、コレクション クラス オブジェクトに格納されている文字列に関連する静的関数が用意されています。  文字列オブジェクトは参照として処理されます。|atlcoll.h|  
|[CThreadPool クラス](../Topic/CThreadPool%20Class.md)|このクラスには、ワーク アイテムのキューを処理するワーカー スレッドのプールが用意されています。|atlutil.h|  
|[CTokenGroups](../../atl/reference/ctokengroups-class.md)|このクラスは、**TOKEN\_GROUPS** 構造体のラッパー クラスです。|atlsecurity.h|  
|[CTokenPrivileges](../../atl/reference/ctokenprivileges-class.md)|このクラスは、**TOKEN\_PRIVILEGES** 構造体のラッパー クラスです。|atlsecurity.h|  
|[CUrl クラス](../../atl/reference/curl-class.md)|このクラスは URL を表します。  URL の各要素をそれぞれ独立に操作して、既存の URL 文字列を解析したり、文字列を新規に組み立てたりできます。|atlutil.h|  
|[CW2AEX](../../atl/reference/cw2aex-class.md)|このクラスは、文字列変換マクロ `CT2AEX`、`CW2TEX`、`CW2CTEX`、`CT2CAEX`、および typedef **CW2A** で使用されます。|atlconv.h|  
|[CW2CWEX](../../atl/reference/cw2cwex-class.md)|このクラスは、文字列変換マクロの `CW2CTEX` と `CT2CWEX`、および typedef **CW2CW** で使用されます。|atlconv.h|  
|[CW2WEX](../../atl/reference/cw2wex-class.md)|このクラスは、文字列変換マクロ `CW2TEX` と `CT2WEX`、および typedef `CW2W` で使用されます。|atlconv.h|  
|[CWin32Heap](../../atl/reference/cwin32heap-class.md)|このクラスは、Win32 ヒープ割り当て関数を使用して、[IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) を実装します。|atlmem.h|  
|[CWindow](../../atl/reference/cwindow-class.md)|このクラスには、ウィンドウを操作するためのメソッドが用意されています。|atlwin.h|  
|[CWindowImpl](../Topic/CWindowImpl%20Class.md)|このクラスには、ウィンドウを作成またはサブクラス化するためのメソッドが用意されています。|atlwin.h|  
|[CWinTraits](../../atl/reference/cwintraits-class.md)|このクラスには、ウィンドウ オブジェクトの作成に使用する、スタイルを標準化するためのメソッドが用意されています。|atlwin.h|  
|[CWinTraitsOR](../../atl/reference/cwintraitsor-class.md)|このクラスには、ウィンドウ オブジェクトの作成に使用する、スタイルを標準化するためのメソッドが用意されています。|atlwin.h|  
|[CWndClassInfo](../../atl/reference/cwndclassinfo-class.md)|このクラスには、ウィンドウ クラスの情報を登録するためのメソッドが用意されています。|atlwin.h|  
|[CWorkerThread クラス](../Topic/CWorkerThread%20Class.md)|このクラスでは、ワーカー スレッドの作成、既存のワーカー スレッドの使用、1 つ以上のカーネル オブジェクト ハンドルの待機、およびハンドルの 1 つがシグナルを送信したときに指定のクライアント関数の実行を行います。|atlutil.h|  
|[IAtlAutoThreadModule](../../atl/reference/iatlautothreadmodule-class.md)|このクラスは、`CreateInstance` メソッドへのインターフェイスを表します。|atlbase.h|  
|[IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md)|このクラスは、メモリ マネージャーへのインターフェイスを表します。|atlmem.h|  
|[IAxWinAmbientDispatch](../../atl/reference/iaxwinambientdispatch-interface.md)|このインターフェイスには、ホストされるコントロールまたはコンテナーの特性を指定するためのメソッドが用意されています。|atlbase.h、ATLIFace.h|  
|[IAxWinAmbientDispatchEx](../../atl/reference/iaxwinambientdispatchex-interface.md)|このインターフェイスは、ホストされるコントロールを補足するアンビエント プロパティを実装します。|atlbase.h、ATLIFace.h|  
|[IAxWinHostWindow](../../atl/reference/iaxwinhostwindow-interface.md)|このインターフェイスには、コントロールとそのホスト オブジェクトを操作するためのメソッドが用意されています。|atlbase.h、ATLIFace.h|  
|[IAxWinHostWindowLic](../../atl/reference/iaxwinhostwindowlic-interface.md)|このインターフェイスには、ライセンスされたコントロールとそのホスト オブジェクトを操作するためのメソッドが用意されています。|atlbase.h、ATLIFace.h|  
|[ICollectionOnSTLImpl](../../atl/reference/icollectiononstlimpl-class.md)|このクラスには、コレクション クラスで使用するメソッドが用意されています。|atlcom.h|  
|[IConnectionPointContainerImpl](../Topic/IConnectionPointContainerImpl%20Class.md)|このクラスは、[IConnectionPointImpl](../Topic/IConnectionPointImpl%20Class.md) オブジェクトのコレクションを管理するコネクション ポイント コンテナーを実装します。|atlcom.h|  
|[IConnectionPointImpl](../Topic/IConnectionPointImpl%20Class.md)|このクラスは、コネクション ポイントを実装します。|atlcom.h|  
|[IDataObjectImpl](../../atl/reference/idataobjectimpl-class.md)|このクラスには、汎用データ転送をサポートして接続を管理するためのメソッドが用意されています。|atlctl.h|  
|[IDispatchImpl](../../atl/reference/idispatchimpl-class.md)|このクラスは、デュアル インターフェイスの `IDispatch` 部分の既定の実装を提供します。|atlcom.h|  
|[IDispEventImpl](../../atl/reference/idispeventimpl-class.md)|このクラスは、`IDispatch` メソッドの実装を提供します。|atlcom.h|  
|[IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md)|このクラスは `IDispatch` メソッドの実装を提供しますが、タイプ ライブラリからはタイプ情報が取得されません。|atlcom.h|  
|[IDocHostUIHandlerDispatch](../Topic/IDocHostUIHandlerDispatch%20Interface.md)|Microsoft の HTML 解析エンジンおよび描画エンジンへのインターフェイスです。|atlbase.h、ATLIFace.h|  
|[IEnumOnSTLImpl](../../atl/reference/ienumonstlimpl-class.md)|このクラスは、STL コレクションに基づいた列挙子インターフェイスを定義します。|atlcom.h|  
|[IObjectSafetyImpl](../../atl/reference/iobjectsafetyimpl-class.md)|このクラスは、`IObjectSafety` インターフェイスの既定の実装を提供して、クライアント側でオブジェクトの安全レベルを取得および設定できるようにします。|atlctl.h|  
|[IObjectWithSiteImpl](../../atl/reference/iobjectwithsiteimpl-class.md)|このクラスには、オブジェクトとそのサイトとの情報のやり取りを可能にするメソッドが用意されています。|atlcom.h|  
|[IOleControlImpl](../../atl/reference/iolecontrolimpl-class.md)|このクラスは、**IOleControl** インターフェイスの既定の実装を提供し、**IUnknown** を実装します。|atlctl.h|  
|[IOleInPlaceActiveObjectImpl](../../atl/reference/ioleinplaceactiveobjectimpl-class.md)|このクラスには、埋め込み先コントロールとそのコンテナーとの情報のやり取りを支援するメソッドが用意されています。|atlctl.h|  
|[IOleInPlaceObjectWindowlessImpl](../../atl/reference/ioleinplaceobjectwindowlessimpl-class.md)|このクラスは **IUnknown** を実装します。また、ウィンドウなしのコントロールでもウィンドウ メッセージの受け取りやドラッグ アンド ドロップ処理を可能にするメソッドが用意されています。|atlctl.h|  
|[IOleObjectImpl](../../atl/reference/ioleobjectimpl-class.md)|このクラスは **IUnknown** を実装します。また、コンテナーがコントロールと情報をやり取りするための基本インターフェイスとなります。|atlctl.h|  
|[IPerPropertyBrowsingImpl](../Topic/IPerPropertyBrowsingImpl%20Class.md)|このクラスは **IUnknown** を実装します。また、オブジェクトのプロパティ ページ内の情報にクライアントからアクセスできるようにします。|atlctl.h|  
|[IPersistPropertyBagImpl](../../atl/reference/ipersistpropertybagimpl-class.md)|このクラスは **IUnknown** を実装します。オブジェクトは、そのプロパティをクライアントが提供するプロパティ バッグに保存できます。|atlcom.h|  
|[IPersistStorageImpl](../../atl/reference/ipersiststorageimpl-class.md)|このクラスは、[IPersistStorage](http://msdn.microsoft.com/library/windows/desktop/ms679731) インターフェイスを実装します。|atlcom.h|  
|[IPersistStreamInitImpl](../../atl/reference/ipersiststreaminitimpl-class.md)|このクラスは、**IUnknown** を実装し、[IPersistStreamInit](http://msdn.microsoft.com/library/windows/desktop/ms682273) インターフェイスの既定の実装を提供します。|atlcom.h|  
|[IPointerInactiveImpl](../../atl/reference/ipointerinactiveimpl-class.md)|このクラスは、**IUnknown** および [IPointerInactive](http://msdn.microsoft.com/library/windows/desktop/ms693712) インターフェイス メソッドを実装します。|atlctl.h|  
|[IPropertyNotifySinkCP](../../atl/reference/ipropertynotifysinkcp-class.md)|このクラスは、[IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638) インターフェイスを接続可能オブジェクトのアウトゴーイング インターフェイスとして公開します。|atlctl.h|  
|[IPropertyPage2Impl](../../atl/reference/ipropertypage2impl-class.md)|このクラスは、**IUnknown** を実装し、[IPropertyPageImpl](../../atl/reference/ipropertypageimpl-class.md) の既定の実装を継承します。|atlctl.h|  
|[IPropertyPageImpl](../../atl/reference/ipropertypageimpl-class.md)|このクラスは、**IUnknown** を実装し、[IPropertyPage](http://msdn.microsoft.com/library/windows/desktop/ms691246) インターフェイスの既定の実装を提供します。|atlctl.h|  
|[IProvideClassInfo2Impl](../../atl/reference/iprovideclassinfo2impl-class.md)|このクラスは、[IProvideClassInfo](http://msdn.microsoft.com/library/windows/desktop/ms687303) メソッドと [IProvideClassInfo2](http://msdn.microsoft.com/library/windows/desktop/ms693764) メソッドの既定の実装を提供します。|atlcom.h|  
|[IQuickActivateImpl](../../atl/reference/iquickactivateimpl-class.md)|このクラスは、コンテナーのコントロールの初期化を結合して 1 つの呼び出しにします。|atlctl.h|  
|[IRunnableObjectImpl](../../atl/reference/irunnableobjectimpl-class.md)|このクラスは、**IUnknown** を実装し、[IRunnableObject](http://msdn.microsoft.com/library/windows/desktop/ms692783) インターフェイスの既定の実装を提供します。|atlctl.h|  
|[IServiceProviderImpl](../../atl/reference/iserviceproviderimpl-class.md)|このクラスは、`IServiceProvider` インターフェイスの既定の実装を提供します。|atlcom.h|  
|[ISpecifyPropertyPagesImpl](../Topic/ISpecifyPropertyPagesImpl%20Class.md)|このクラスは、**IUnknown** を実装し、[ISpecifyPropertyPages](http://msdn.microsoft.com/library/windows/desktop/ms695217) インターフェイスの既定の実装を提供します。|atlcom.h|  
|[ISupportErrorInfoImpl](../../atl/reference/isupporterrorinfoimpl-class.md)|このクラスには、`ISupportErrorInfo Interface` インターフェイスの既定の実装が用意されています。このクラスを使用できるのは、1 つのインターフェイスだけがオブジェクトでエラーを生成するときです。|atlcom.h|  
|[IThreadPoolConfig インターフェイス](../../atl/reference/ithreadpoolconfig-interface.md)|このインターフェイスには、スレッド プールを設定するメソッドが用意されています。|atlutil.h|  
|[IViewObjectExImpl](../../atl/reference/iviewobjecteximpl-class.md)|このクラスは **IUnknown** を実装します。また、[IViewObject](http://msdn.microsoft.com/library/windows/desktop/ms680763)、[IViewObject2](http://msdn.microsoft.com/library/windows/desktop/ms691318)、および [IViewObjectEx](http://msdn.microsoft.com/library/windows/desktop/ms682375) の各インターフェイスの既定の実装を提供します。|atlctl.h|  
|[IWorkerThreadClient インターフェイス](../Topic/IWorkerThreadClient%20Interface.md)|`IWorkerThreadClient` インターフェイスは、[CWorkerThread](../Topic/CWorkerThread%20Class.md) クラスのクライアントによって実装されています。|atlutil.h|  
|[\_U\_MENUorID](../../atl/reference/u-menuorid-class.md)|このクラスには、**CreateWindow** と **CreateWindowEx** のラッパー クラスが用意されています。|atlwin.h|  
|[\_U\_RECT](../../atl/reference/u-rect-class.md)|この引数アダプター クラスによって、ポインターとして実装される関数に `RECT` ポインターまたは参照を渡すことができます。|atlwin.h|  
|[\_U\_STRINGorID](../../atl/reference/u-stringorid-class.md)|この引数アダプター クラスによって、呼び出し元で **MAKEINTRESOURCE** マクロを使用して ID を文字列に変換せずに、リソース名 \(`LPCTSTR`\) またはリソース ID \(**UINT**\) を関数に渡すことができます。|atlwin.h|  
|[Win32ThreadTraits](../Topic/Win32ThreadTraits%20Class.md)|このクラスには、Windows スレッド用の作成関数が用意されています。  スレッドが CRT 関数を使用しない場合は、このクラスを使用します。|atlbase.h|  
  
## 参照  
 [ATL COM デスクトップ コンポーネント](../../atl/atl-com-desktop-components.md)   
 [関数](../../atl/reference/atl-functions.md)   
 [グローバル変数](../Topic/ATL%20Global%20Variables.md)   
 [構造体](../../atl/reference/atl-structures.md)   
 [typedef](../../atl/reference/atl-typedefs.md)   
 [クラスの概要](../../atl/atl-class-overview.md)