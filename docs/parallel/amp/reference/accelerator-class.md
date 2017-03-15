---
title: "accelerator クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- amprt/Concurrency::accelerator
dev_langs:
- C++
helpviewer_keywords:
- accelerator class
ms.assetid: 37eed593-cf87-4611-9cdc-e98df6c2377a
caps.latest.revision: 29
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: fc190feb08d9b221cd1cc21a9c91ad567c86c848
ms.openlocfilehash: b1bdd7f6979094658d1de6f9690bc44dc50ee8bb
ms.lasthandoff: 02/24/2017

---
# <a name="accelerator-class"></a>accelerator クラス
アクセラレータは、データ並列計算用に最適化されたハードウェアの機能です。 アクセラレータは、PCIe バス (GPU など) にアタッチされているデバイスである場合や主要 CPU の拡張命令セットである場合があります。  
  
## <a name="syntax"></a>構文  
  
```  
class accelerator;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[アクセラレータのコンス トラクター](#ctor)|`accelerator` クラスの新しいインスタンスを初期化します。|  
|[~ accelerator デストラクター](#ctor)|`accelerator` オブジェクトを破棄します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[create_view メソッド](#create_view)|このアクセラレータの `accelerator_view` オブジェクトを作成して返します。|  
|[get_all メソッド](#get_all)|使用可能なすべてのアクセラレータを表す `accelerator` オブジェクトのベクターを返します。|  
|[get_auto_selection_view メソッド](#get_auto_selection_view)|自動選択 `accelerator_view` を返します。|  
|[get_dedicated_memory メソッド](#get_dedicated_memory)|`accelerator` の専用のメモリ (KB 単位) を返します。|  
|[get_default_cpu_access_type メソッド](#get_default_cpu_access_type)|既定値を返す[access_type](concurrency-namespace-enums-amp.md#access_type)このアクセラレータで作成されるバッファーのです。|  
|[get_default_view メソッド](#get_default_view)|`accelerator_view` に関連付けられている既定の `accelerator` オブジェクトを返します。|  
|[get_description メソッド](#get_description)|`accelerator` デバイスの短い説明を返します。|  
|[get_device_path メソッド](#get_device_path)|デバイスのパスを返します。|  
|[get_has_display メソッド](#get_has_display)|`accelerator` がディスプレイにアタッチされるかどうかを決定します。|  
|[get_is_debug メソッド](#get_is_debug)|`accelerator` が広範なエラー レポートに有効なデバッグ レイヤーを持つかどうかを決定します。|  
|[get_is_emulated メソッド](#get_is_emulated)|`accelerator` がエミュレートされるかどうかを決定します。|  
|[get_supports_cpu_shared_memory メソッド](#get_supports_cpu_shared_memory)|`accelerator` が共有メモリをサポートするかどうかを決定します|  
|[get_supports_double_precision メソッド](#get_supports_double_precision)|`accelerator` がディスプレイにアタッチされるかどうかを決定します。|  
|[get_supports_limited_double_precision メソッド](#get_supports_limited_double_precision)|`accelerator` が倍精度サポートを制限するかどうかを決定します。|  
|[get_version メソッド](#get_version)|`accelerator` のバージョンを返します。|  
|[set_default メソッド](#set_default)|既定のアクセラレータのパスを返します。|  
|[set_default_cpu_access_type メソッド](#set_default_cpu_access_type)|既定の CPU 設定[access_type](concurrency-namespace-enums-amp.md#access_type)配列、およびこれに行われる暗黙的なメモリ割り当て`accelerator`します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[operator! = 演算子](#operator_neq)|この `accelerator` オブジェクトを別のオブジェクトと比較し、同じ場合は `false` を返し、それ以外の場合は `true` を返します。|  
|[operator = 演算子](#operator_eq)|指定された `accelerator` オブジェクトの内容をこのオブジェクトにコピーします。|  
|[operator = 演算子](#operator_eq_eq)|この `accelerator` オブジェクトを別のオブジェクトと比較し、同じ場合は `true` を返し、それ以外の場合は `false` を返します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[cpu_accelerator データ メンバー](#cpu_accelerator)|CPU `accelerator` の文字列定数を取得します。|  
|[dedicated_memory データ メンバー](#dedicated_memory)|`accelerator` の専用のメモリ (KB 単位) を取得します。|  
|[default_accelerator データ メンバー](#default_accelerator)|既定の `accelerator` の文字列定数を取得します。|  
|[default_cpu_access_type データ メンバー](#default_cpu_access_type)|取得または設定の既定の CPU [access_type](concurrency-namespace-enums-amp.md#access_type)配列、およびこれに行われる暗黙的なメモリ割り当て`accelerator`します。|  
|[default_view データ メンバー](#default_view)|`accelerator_view` に関連付けられている既定の `accelerator` オブジェクトを取得します。|  
|[データ メンバーの説明](#description)|`accelerator` デバイスの短い説明を取得します。|  
|[device_path データ メンバー](#device_path)|デバイスのパスを取得します。|  
|[direct3d_ref データ メンバー](#direct3d_ref)|Direct3D 参照 `accelerator` の文字列定数を取得します。|  
|[direct3d_warp データ メンバー](#direct3d_warp)|文字列の定数を取得、 `accelerator` Streaming SIMD Extensions (SSE) を使用するマルチコア Cpu で C++ AMP コードの実行に使用できるオブジェクトします。|  
|[has_display データ メンバー](#has_display)|`accelerator` がディスプレイにアタッチされているかどうかを示すブール値を取得します。|  
|[is_debug データ メンバー](#is_debug)|`accelerator` に、広範なエラー レポートに有効なデバッグ レイヤーがあるかどうかを示します。|  
|[is_emulated データ メンバー](#is_emulated)|`accelerator` がエミュレートされるかどうかを示します。|  
|[supports_cpu_shared_memory データ メンバー](#supports_cpu_shared_memory)|`accelerator` が共有メモリをサポートするかどうかを示します。|  
|[supports_double_precision データ メンバー](#supports_double_precision)|アクセラレータが倍精度数値演算をサポートするかどうかを示します。|  
|[supports_limited_double_precision データ メンバー](#supports_limited_double_precision)|アクセラレータの倍精度数値演算のサポートが制限されているかどうかを示します。|  
|[バージョン データ メンバー](#version)|`accelerator` のバージョンを取得します。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `accelerator`  
  
## <a name="remarks"></a>コメント  
 アクセラレータは、データ並列計算用に最適化されたハードウェアの機能です。 多くの場合、アクセラレータは独立した GPU ですが、DirectX REF デバイス、WARP (SSE 命令で加速される CPU 側のデバイス)、または CPU 自体などの仮想ホスト側のエンティティでもあることがあります。  
  
 使用できるデバイスをエミュレートすることによって、または既定のデバイス、参照デバイス、または WARP デバイスを取得することによって、`accelerator` オブジェクトを構築することができます。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** amprt.h  
  
 **名前空間:** Concurrency  
  
##  <a name="dtor"></a></a> ~ アクセラレータ 

 `accelerator` オブジェクトを破棄します。  
  
```  
~accelerator();
```  
  
### <a name="return-value"></a>戻り値  
  
##  <a name="a-namectora-accelerator"></a><a name="ctor"></a>アクセラレータ 

 新しいインスタンスを初期化、 [accelerator クラス](accelerator-class.md)します。  
  
```  
accelerator();

 
explicit accelerator(const std::wstring& _Device_path);

 
accelerator(const accelerator& _Other);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Device_path`  
 物理デバイスのパスです。  
  
 `_Other`  
 コピーするアクセラレータです。  
  
##  <a name="a-namecpuacceleratora-cpuaccelerator"></a><a name="cpu_accelerator"></a>cpu_accelerator 

 CPU アクセラレータの文字列定数を取得します。  
  
```  
static const wchar_t cpu_accelerator[];  
```  
  
##  <a name="a-namecreateviewa-createview"></a><a name="create_view"></a>create_view 

 作成して返します、`accelerator_view`指定されたキュー モードを使用して、このアクセラレータでのオブジェクト。 キュー モードが指定されていない場合、新しい`accelerator_view`を使用して、 [queuing_mode::immediate](concurrency-namespace-enums-amp.md#queuing_mode)キュー モード。  
  
```  
accelerator_view create_view(queuing_mode qmode = queuing_mode_automatic);
```  
  
### <a name="parameters"></a>パラメーター  
 `qmode`  
 キュー モード。  
  
### <a name="return-value"></a>戻り値  
 新しい`accelerator_view`指定されたキュー モードを使用して、このアクセラレータでのオブジェクト。  
  
##  <a name="a-namededicatedmemorya-dedicatedmemory"></a><a name="dedicated_memory"></a>dedicated_memory 

 `accelerator` の専用のメモリ (KB 単位) を取得します。  
  
```  
__declspec(property(get= get_dedicated_memory)) size_t dedicated_memory;  
```  
  
##  <a name="a-namedefaultacceleratora-defaultaccelerator"></a><a name="default_accelerator"></a>default_accelerator 

 既定の `accelerator` の文字列定数を取得します。  
  
```  
static const wchar_t default_accelerator[];  
```  
  
##  <a name="a-namedefaultcpuaccesstypea-defaultcpuaccesstype"></a><a name="default_cpu_access_type"></a>default_cpu_access_type 

 既定の cpu [access_type](concurrency-namespace-enums-amp.md#access_type)配列および暗黙的なメモリの割り当てに対するこの`accelerator`します。  
  
```  
__declspec(property(get= get_default_cpu_access_type)) access_type default_cpu_access_type;  
```  
  
##  <a name="a-namedefaultviewa-defaultview"></a><a name="default_view"></a>default_view 

 関連付けられている既定のアクセラレータ ビューを取得、`accelerator`です。  
  
```  
__declspec(property(get= get_default_view)) accelerator_view default_view;  
```  
  
##  <a name="a-namedescriptiona-description"></a><a name="description"></a>説明 

 `accelerator` デバイスの短い説明を取得します。  
  
```  
__declspec(property(get= get_description)) std::wstring description;  
```  
  
##  <a name="a-namedevicepatha-devicepath"></a><a name="device_path"></a>device_path 

 アクセラレータのパスを取得します。 パスは、システム上で一意です。  
  
```  
__declspec(property(get= get_device_path)) std::wstring device_path;  
```  
  
##  <a name="a-namedirect3drefa-direct3dref"></a><a name="direct3d_ref"></a>direct3d_ref 

 Direct3D 参照アクセラレータの文字列定数を取得します。  
  
```  
static const wchar_t direct3d_ref[];  
```  
  
##  <a name="a-namedirect3dwarpa-direct3dwarp"></a><a name="direct3d_warp"></a>direct3d_warp 

 文字列の定数を取得、 `accelerator` Streaming SIMD Extensions (SSE) を使用するマルチコア Cpu で C++ AMP コードの実行に使用できるオブジェクトします。  
  
```  
static const wchar_t direct3d_warp[];  
```  
  
##  <a name="a-namegetalla-getall"></a><a name="get_all"></a>get_all 

 使用可能なすべてのアクセラレータを表す `accelerator` オブジェクトのベクターを返します。  
  
```  
static inline std::vector<accelerator> get_all();
```  
  
### <a name="return-value"></a>戻り値  
 使用できるアクセラレータのベクター  
  
##  <a name="a-namegetautoselectionviewa-getautoselectionview"></a><a name="get_auto_selection_view"></a>get_auto_selection_view 

 ランタイムによって自動的に選択される parallel_for_each カーネルを実行するためにターゲットの accelerator_view で parallel_for_each ターゲット結果として指定される場合、自動選択の accelerator_view を返します。 その他のすべての目的については、このメソッドで返される accelerator_view は、既定のアクセラレータの既定の accelerator_view と同じです。  
  
```  
static accelerator_view __cdecl get_auto_selection_view();
```  
  
### <a name="return-value"></a>戻り値  
 自動選択の accelerator_view。  
  
##  <a name="a-namegetdedicatedmemorya-getdedicatedmemory"></a><a name="get_dedicated_memory"></a>get_dedicated_memory 

 `accelerator` の専用のメモリ (KB 単位) を返します。  
  
```  
size_t get_dedicated_memory() const;

 
```  
  
### <a name="return-value"></a>戻り値  
 専用のメモリ、 `accelerator`、(キロバイト単位)。  
  
##  <a name="a-namegetdefaultcpuaccesstypea-getdefaultcpuaccesstype"></a><a name="get_default_cpu_access_type"></a>get_default_cpu_access_type 

 このアクセラレータで作成されるバッファーの既定の CPU access_type を取得します  
  
```  
access_type get_default_cpu_access_type() const;

 
```  
  
### <a name="return-value"></a>戻り値  
 このアクセラレータで作成されるバッファーの既定の CPU access_type。  
  
##  <a name="a-namegetdefaultviewa-getdefaultview"></a><a name="get_default_view"></a>get_default_view 

 `accelerator_view` に関連付けられている既定の `accelerator` オブジェクトを返します。  
  
```  
accelerator_view get_default_view() const;

 
```  
  
### <a name="return-value"></a>戻り値  
 既定値`accelerator_view`オブジェクトに関連付けられている、`accelerator`です。  
  
##  <a name="a-namegetdescriptiona-getdescription"></a><a name="get_description"></a>get_description 

 `accelerator` デバイスの短い説明を返します。  
  
```  
std::wstring get_description() const;

 
```  
  
### <a name="return-value"></a>戻り値  
 簡単な説明、`accelerator`デバイスです。  
  
##  <a name="a-namegetdevicepatha-getdevicepath"></a><a name="get_device_path"></a>get_device_path 

 アクセラレータのパスを返します。 パスは、システム上で一意です。  
  
```  
std::wstring get_device_path() const;

 
```  
  
### <a name="return-value"></a>戻り値  
 一意のデバイスをシステム全体にわたるインスタンスのパス。  
  
##  <a name="a-namegethasdisplaya-gethasdisplay"></a><a name="get_has_display"></a>get_has_display 

 示すブール値を返すかどうか、`accelerator`ディスプレイに出力できます。  
  
```  
bool get_has_display() const;

 
```  
  
### <a name="return-value"></a>戻り値  
 `true` がディスプレイに出力できる場合は `accelerator`。それ以外の場合は `false`。  
  
##  <a name="a-namegetisdebuga-getisdebug"></a><a name="get_is_debug"></a>get_is_debug 

 `accelerator` が広範なエラー レポートに有効なデバッグ レイヤーを持つかどうかを決定します。  
  
```  
bool get_is_debug() const;

 
```  
  
### <a name="return-value"></a>戻り値  
 `true` に、広範なエラー レポートに有効なデバッグ レイヤーがある場合、`accelerator`。 それ以外の場合は `false`。  
  
##  <a name="a-namegetisemulateda-getisemulated"></a><a name="get_is_emulated"></a>get_is_emulated 

 `accelerator` がエミュレートされるかどうかを決定します。  
  
```  
bool get_is_emulated() const;

 
```  
  
### <a name="return-value"></a>戻り値  
 `true` がエミュレートされる場合、`accelerator`。 それ以外の場合は `false`。  
  
##  <a name="a-namegetsupportscpusharedmemorya-getsupportscpusharedmemory"></a><a name="get_supports_cpu_shared_memory"></a>get_supports_cpu_shared_memory 

 アクセラレータがアクセラレータと CPU の両方からアクセスできるメモリをサポートするかどうかを示すブール値を返します。  
  
```  
bool get_supports_cpu_shared_memory() const;

 
```  
  
### <a name="return-value"></a>戻り値  
 アクセラレータが CPU 共有メモリをサポートする場合は `true`、それ以外の場合は `false`。  
  
##  <a name="a-namegetsupportsdoubleprecisiona-getsupportsdoubleprecision"></a><a name="get_supports_double_precision"></a>get_supports_double_precision 

 アクセラレータが融合型積和演算 (FMA)、除算、逆数、および `int` と `double` 間のキャストなどの倍精度演算をサポートするかどうかを示すブール値を返します。  
  
```  
bool get_supports_double_precision() const;

 
```  
  
### <a name="return-value"></a>戻り値  
 アクセラレータが倍精度演算をサポートする場合は `true`、それ以外の場合は `false`。  
  
##  <a name="a-namegetsupportslimiteddoubleprecisiona-getsupportslimiteddoubleprecision"></a><a name="get_supports_limited_double_precision"></a>get_supports_limited_double_precision 

 アクセラレータが倍精度演算のサポートを制限されているかどうかを示すブール値を返します。 アクセラレータが一部のみがサポート、乗算定着し、追加 (FMA)、除算、逆数、および間のキャスト`int`と`double`はサポートされていません。  
  
```  
bool get_supports_limited_double_precision() const;

 
```  
  
### <a name="return-value"></a>戻り値  
 `true`アクセラレータの倍精度演算; のサポートが制限されている場合それ以外の場合、`false`です。  
  
##  <a name="a-namegetversiona-getversion"></a><a name="get_version"></a>get_version 

 `accelerator` のバージョンを返します。  
  
```  
unsigned int get_version() const;

 
```  
  
### <a name="return-value"></a>戻り値  
 バージョン、`accelerator`です。  
  
##  <a name="a-namehasdisplaya-hasdisplay"></a><a name="has_display"></a>has_display 

 示すブール値を取得するかどうか、`accelerator`ディスプレイに出力できます。  
  
```  
__declspec(property(get= get_has_display)) bool has_display;  
```  
  
##  <a name="a-nameisdebuga-isdebug"></a><a name="is_debug"></a>is_debug 

 示すブール値を取得するかどうか、`accelerator`広範なエラー レポートに有効なデバッグ レイヤーを持ちます。  
  
```  
__declspec(property(get= get_is_debug)) bool is_debug;  
```  
  
##  <a name="a-nameisemulateda-isemulated"></a><a name="is_emulated"></a>is_emulated 

 示すブール値を取得するかどうか、`accelerator`がエミュレートされます。  
  
```  
__declspec(property(get= get_is_emulated)) bool is_emulated;  
```  
  
##  <a name="a-nameoperatorneqa-operator"></a><a name="operator_neq"></a>operator! = 

 この `accelerator` オブジェクトを別のオブジェクトと比較し、同じ場合は `false` を返し、それ以外の場合は `true` を返します。  
  
```  
bool operator!= (const accelerator& _Other) const;

 
```  
  
### <a name="parameters"></a>パラメーター  
 `_Other`  
 `accelerator`これと比較するオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 `false`場合は、2 つ`accelerator`オブジェクトが等しい。 そうしないと、`true`です。  
  
##  <a name="a-nameoperatoreqa-operator"></a><a name="operator_eq"></a>演算子 = 

 指定された `accelerator` オブジェクトの内容をこのオブジェクトにコピーします。  
  
```  
accelerator& operator= (const accelerator& _Other);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Other`  
 コピー元の `accelerator` オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 この `accelerator` オブジェクトへの参照。  
  
##  <a name="a-nameoperatoreqeqa-operator"></a><a name="operator_eq_eq"></a>演算子 = = 

 この `accelerator` オブジェクトを別のオブジェクトと比較し、同じ場合は `true` を返し、それ以外の場合は `false` を返します。  
  
```  
bool operator== (const accelerator& _Other) const;

 
```  
  
### <a name="parameters"></a>パラメーター  
 `_Other`  
 `accelerator`これと比較するオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 `true`場合、その他の`accelerator`オブジェクトはこれと同じ`accelerator`オブジェクト。 それ以外の場合、`false`です。  
  
##  <a name="a-namesetdefaulta-setdefault"></a><a name="set_default"></a>set_default 

 暗黙的に既定のアクセラレータを使用するすべての操作に使用する既定のアクセラレータを設定します。 このメソッドは、ランタイムによって選択された既定のアクセラレータが暗黙的に既定のアクセラレータを使用する操作で既に使用されていない場合にのみ正常に終了します  
  
```  
static inline bool set_default(std::wstring _Path);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Path`  
 アクセラレータへのパス。  
  
### <a name="return-value"></a>戻り値  
 既定のアクセラレータの設定で呼び出しが成功した場合、`true`。 それ以外の場合は `false`。  
  
##  <a name="a-namesetdefaultcpuaccesstypea-setdefaultcpuaccesstype"></a><a name="set_default_cpu_access_type"></a>set_default_cpu_access_type 

 このアクセラレータで作成される配列、またはこのアクセラレータでアクセスされる array_views の一部としての暗黙的なメモリ割り当てに、既定の CPU access_type を設定します。 アクセラレータの default_cpu_access_type がこのメソッドへの前の呼び出しによってまだオーバーライドされておらず、このアクセラレータのために default_cpu_access_type を選択したランタイムが、配列の割り当てまたはこのアクセラレータでアクセスされる array_view の暗黙的なメモリ割り当てバッキングにまだ使用されていない場合にのみ、このメソッドは成功します。  
  
```  
bool set_default_cpu_access_type(access_type _Default_cpu_access_type);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Default_cpu_access_type`  
 このアクセラレータの array/array_view メモリ割り当てに使用される既定の CPU access_type。  
  
### <a name="return-value"></a>戻り値  
 アクセラレータの既定の CPU access_type が正常に設定されたかどうかを示すブール値。  
  
##  <a name="a-namesupportscpusharedmemorya-supportscpusharedmemory"></a><a name="supports_cpu_shared_memory"></a>supports_cpu_shared_memory 

 `accelerator` が共有メモリをサポートしているかどうか示すブール値を取得します。  
  
```  
__declspec(property(get= get_supports_cpu_shared_memory)) bool supports_cpu_shared_memory;  
```  
  
##  <a name="a-namesupportsdoubleprecisiona-supportsdoubleprecision"></a><a name="supports_double_precision"></a>supports_double_precision 

 アクセラレータが倍精度浮動小数点演算をサポートするかどうかを示すブール値を取得します。  
  
```  
__declspec(property(get= get_supports_double_precision)) bool supports_double_precision;  
```  
  
##  <a name="a-namesupportslimiteddoubleprecisiona-supportslimiteddoubleprecision"></a><a name="supports_limited_double_precision"></a>supports_limited_double_precision 

 アクセラレータが倍精度演算のサポートを制限されているかどうかを示すブール値を取得します。 アクセラレータが一部のみがサポート、乗算定着し、追加 (FMA)、除算、逆数、および間のキャスト`int`と`double`はサポートされていません。  
  
```  
__declspec(property(get= get_supports_limited_double_precision)) bool supports_limited_double_precision;  
```  
  
##  <a name="a-nameversiona-version"></a><a name="version"></a>バージョン 

 `accelerator` のバージョンを取得します。  
  
```  
__declspec(property(get= get_version)) unsigned int version;  
```  
  
##  <a name="dtor"></a></a> ~ accelerator_view 

 破棄、 [accelerator_view](accelerator-view-class.md)オブジェクトです。  
  
```  
~accelerator_view();
```  
  
### <a name="return-value"></a>戻り値  
  
##  <a name="a-nameacceleratora-accelerator"></a><a name="accelerator"></a>アクセラレータ 

 取得、`accelerator`のオブジェクト、 [accelerator_view](accelerator-view-class.md)オブジェクトです。  
  
```  
__declspec(property(get= get_accelerator)) Concurrency::accelerator accelerator;  
```  
  
##  <a name="a-namectora-acceleratorview"></a><a name="ctor"></a>accelerator_view 

 新しいインスタンスを初期化、 [accelerator_view](accelerator-view-class.md)クラス、既存のコピーを`accelerator_view`オブジェクトです。  
  
```  
accelerator_view(const accelerator_view& _Other);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Other`  
 コピーする `accelerator_view` オブジェクト。  
  
##  <a name="a-namecreatemarkera-createmarker"></a><a name="create_marker"></a>create_marker 

 これまでにこの `accelerator_view` オブジェクトに送信されたすべてのコマンドの完了を追跡するために予定を返します。  
  
```  
concurrency::completion_future create_marker();
```  
  
### <a name="return-value"></a>戻り値  
 これまでこの `accelerator_view` オブジェクトに送信されたすべてのコマンドの完了を追跡するための予定です。  
  
##  <a name="a-nameflusha-flush"></a><a name="flush"></a>フラッシュ 

 キューに格納されたすべての保留中のコマンドを送信する、 [accelerator_view](accelerator-view-class.md)実行するためのアクセラレータへのオブジェクト。  
  
```  
void flush();
```  
  
### <a name="return-value"></a>戻り値  
 `void` を返します。  
  
##  <a name="a-namegetacceleratora-getaccelerator"></a><a name="get_accelerator"></a>get_accelerator 

 返します。、`accelerator`のオブジェクト、 [accelerator_view](accelerator-view-class.md)オブジェクトです。  
  
```  
accelerator get_accelerator() const;

 
```  
  
### <a name="return-value"></a>戻り値  
 `accelerator`のオブジェクト、`accelerator_view`オブジェクトです。  
  
##  <a name="a-namegetisautoselectiona-getisautoselection"></a><a name="get_is_auto_selection"></a>get_is_auto_selection 

 選択を示すかどうか、ランタイムは自動的に適切なアクセラレータ accelerator_view に渡されるブール値を返す、 [parallel_for_each](../../../parallel/concrt/reference/concurrency-namespace-functions.md#parallel_for_each)します。  
  
```  
bool get_is_auto_selection() const;

 
```  
  
### <a name="return-value"></a>戻り値  
 ランタイムが自動的に適切なアクセラレータを選択する場合は `true`、それ以外の場合は `false`。  
  
##  <a name="a-namegetisdebuga-getisdebug"></a><a name="get_is_debug"></a>get_is_debug 

 示すブール値を返すかどうか、 [accelerator_view](accelerator-view-class.md)広範なエラー レポートに有効なデバッグ レイヤーが付きます。  
  
```  
bool get_is_debug() const;

 
```  
  
### <a name="return-value"></a>戻り値  
 示すブール値かどうか、`accelerator_view`広範なエラー レポートに有効なデバッグ レイヤーが付きます。  
  
##  <a name="a-namegetqueuingmodea-getqueuingmode"></a><a name="get_queuing_mode"></a>get_queuing_mode 

 キュー モードを返す、 [accelerator_view](accelerator-view-class.md)オブジェクトです。  
  
```  
queuing_mode get_queuing_mode() const;

 
```  
  
### <a name="return-value"></a>戻り値  
 キュー モード、`accelerator_view`オブジェクトです。  
  
##  <a name="a-namegetversiona-getversion"></a><a name="get_version"></a>get_version 

 バージョンを返す、 [accelerator_view](accelerator-view-class.md)します。  
  
```  
unsigned int get_version() const;

 
```  
  
### <a name="return-value"></a>戻り値  
 バージョン、`accelerator_view`です。  
  
##  <a name="a-nameisautoselectiona-isautoselection"></a><a name="is_auto_selection"></a>is_auto_selection 

 選択を示すかどうか、ランタイムは自動的に適切なアクセラレータ accelerator_view に渡されるブール値を取得、 [parallel_for_each](../../../parallel/concrt/reference/concurrency-namespace-functions.md#parallel_for_each)します。  
  
```  
__declspec(property(get= get_is_auto_selection)) bool is_auto_selection;  
```  
  
##  <a name="a-nameisdebuga-isdebug"></a><a name="is_debug"></a>is_debug 

 示すブール値を取得するかどうか、 [accelerator_view](accelerator-view-class.md)広範なエラー レポートに有効なデバッグ レイヤーが付きます。  
  
```  
__declspec(property(get= get_is_debug)) bool is_debug;  
```  
  
##  <a name="a-nameoperatorneqa-operator"></a><a name="operator_neq"></a>operator! = 

 この比較[accelerator_view](accelerator-view-class.md)と他のオブジェクトを返します`false`は同じである場合、それ以外の場合を返します`true`します。  
  
```  
bool operator!= (const accelerator_view& _Other) const;

 
```  
  
### <a name="parameters"></a>パラメーター  
 `_Other`  
 `accelerator_view`これと比較するオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 2 つのオブジェクトが同一である場合は `false`。それ以外の場合は `true`。  
  
##  <a name="a-nameoperatoreqa-operator"></a><a name="operator_eq"></a>演算子 = 

 指定した内容をコピー [accelerator_view](accelerator-view-class.md)をこのオブジェクトです。  
  
```  
accelerator_view& operator= (const accelerator_view& _Other);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Other`  
 コピー元の `accelerator_view` オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 変更したへの参照を`accelerator_view`オブジェクトです。  
  
##  <a name="a-nameoperatoreqeqa-operator"></a><a name="operator_eq_eq"></a>演算子 = = 

 この比較[accelerator_view](accelerator-view-class.md)と他のオブジェクトを返します`true`は同じである場合、それ以外の場合を返します`false`します。  
  
```  
bool operator== (const accelerator_view& _Other) const;

 
```  
  
### <a name="parameters"></a>パラメーター  
 `_Other`  
 `accelerator_view`これと比較するオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 2 つのオブジェクトが同一である場合は `true`。それ以外の場合は `false`。  
  
##  <a name="a-namequeuingmodea-queuingmode"></a><a name="queuing_mode"></a>queuing_mode 

 キュー モードを取得、 [accelerator_view](accelerator-view-class.md)オブジェクトです。  
  
```  
__declspec(property(get= get_queuing_mode)) Concurrency::queuing_mode queuing_mode;  
```  
  
##  <a name="a-nameversiona-version"></a><a name="version"></a>バージョン 

 バージョンを取得、 [accelerator_view](accelerator-view-class.md)します。  
  
```  
__declspec(property(get= get_version)) unsigned int version;  
```  
  
##  <a name="a-namewaita-wait"></a><a name="wait"></a>待機 

 送信されたすべてのコマンドの待機、 [accelerator_view](accelerator-view-class.md)を完了するオブジェクト。  
  
```  
void wait();
```  
  
### <a name="return-value"></a>戻り値  
 `void` を返します。  
  
## <a name="see-also"></a>関連項目  
 [同時実行 Namespace (C++ AMP)](concurrency-namespace-cpp-amp.md)

