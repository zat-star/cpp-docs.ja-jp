---
title: "accelerator クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "amprt/Concurrency::accelerator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "accelerator クラス"
ms.assetid: 37eed593-cf87-4611-9cdc-e98df6c2377a
caps.latest.revision: 29
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 29
---
# accelerator クラス
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

アクセラレータは、データ並列計算用に最適化されたハードウェアの機能です。 アクセラレータは、PCIe バス (GPU など) にアタッチされているデバイスである場合や主要 CPU の拡張命令セットである場合があります。  
  
## <a name="syntax"></a>構文  
  
```  
class accelerator;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[accelerator::accelerator コンス トラクター](#accelerator__accelerator_constructor)|`accelerator` クラスの新しいインスタンスを初期化します。|  
|[accelerator:: ~ accelerator デストラクター](#accelerator___dtoraccelerator_destructor)|`accelerator` オブジェクトを破棄します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[accelerator::create_view メソッド](#accelerator__create_view_method)|このアクセラレータの `accelerator_view` オブジェクトを作成して返します。|  
|[accelerator::get_all メソッド](#accelerator__get_all_method)|使用可能なすべてのアクセラレータを表す `accelerator` オブジェクトのベクターを返します。|  
|[accelerator::get_auto_selection_view メソッド](#accelerator__get_auto_selection_view_method)|自動選択 `accelerator_view` を返します。|  
|[accelerator::get_dedicated_memory メソッド](#accelerator__get_dedicated_memory_method)|`accelerator` の専用のメモリ (KB 単位) を返します。|  
|[accelerator::get_default_cpu_access_type メソッド](#accelerator__get_default_cpu_access_type_method)|既定値を返す [access_type](../Topic/concurrency%20namespace%20enums.md#access_type) このアクセラレータで作成されるバッファーのです。|  
|[accelerator::get_default_view メソッド](#accelerator__get_default_view_method)|`accelerator_view` に関連付けられている既定の `accelerator` オブジェクトを返します。|  
|[accelerator::get_description メソッド](#accelerator__get_description_method)|`accelerator` デバイスの短い説明を返します。|  
|[accelerator::get_device_path メソッド](#accelerator__get_device_path_method)|デバイスのパスを返します。|  
|[accelerator::get_has_display メソッド](#accelerator__get_has_display_method)|`accelerator` がディスプレイにアタッチされるかどうかを決定します。|  
|[accelerator::get_is_debug メソッド](#accelerator__get_is_debug_method)|`accelerator` が広範なエラー レポートに有効なデバッグ レイヤーを持つかどうかを決定します。|  
|[accelerator::get_is_emulated メソッド](#accelerator__get_is_emulated_method)|`accelerator` がエミュレートされるかどうかを決定します。|  
|[accelerator::get_supports_cpu_shared_memory メソッド](#accelerator__get_supports_cpu_shared_memory_method)|`accelerator` が共有メモリをサポートするかどうかを決定します|  
|[accelerator::get_supports_double_precision メソッド](#accelerator__get_supports_double_precision_method)|`accelerator` がディスプレイにアタッチされるかどうかを決定します。|  
|[accelerator::get_supports_limited_double_precision メソッド](#accelerator__get_supports_limited_double_precision_method)|`accelerator` が倍精度サポートを制限するかどうかを決定します。|  
|[accelerator::get_version メソッド](#accelerator__get_version_method)|`accelerator` のバージョンを返します。|  
|[accelerator::set_default メソッド](#accelerator__set_default_method)|既定のアクセラレータのパスを返します。|  
|[accelerator::set_default_cpu_access_type メソッド](#accelerator__set_default_cpu_access_type_method)|既定の CPU 設定 [access_type](../Topic/concurrency%20namespace%20enums.md#access_type) 配列、およびこれに行われる暗黙的なメモリ割り当て `accelerator`します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[accelerator::operator! = 演算子](#accelerator__operator_neq_operator)|この `accelerator` オブジェクトを別のオブジェクトと比較し、同じ場合は `false` を返し、それ以外の場合は `true` を返します。|  
|[accelerator::operator = 演算子](#accelerator__operator_eq_operator)|指定された `accelerator` オブジェクトの内容をこのオブジェクトにコピーします。|  
|[accelerator::operator = 演算子](#accelerator__operator_eq_eq_operator)|この `accelerator` オブジェクトを別のオブジェクトと比較し、同じ場合は `true` を返し、それ以外の場合は `false` を返します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[accelerator::cpu_accelerator データ メンバー](#accelerator__cpu_accelerator_data_member)|CPU `accelerator` の文字列定数を取得します。|  
|[accelerator::dedicated_memory データ メンバー](#accelerator__dedicated_memory_data_member)|`accelerator` の専用のメモリ (KB 単位) を取得します。|  
|[accelerator::default_accelerator データ メンバー](#accelerator__default_accelerator_data_member)|既定の `accelerator` の文字列定数を取得します。|  
|[accelerator::default_cpu_access_type データ メンバー](#accelerator__default_cpu_access_type_data_member)|取得または設定の既定の CPU [access_type](../Topic/concurrency%20namespace%20enums.md#access_type) 配列、およびこれに行われる暗黙的なメモリ割り当て `accelerator`します。|  
|[accelerator::default_view データ メンバー](#accelerator__default_view_data_member)|`accelerator_view` に関連付けられている既定の `accelerator` オブジェクトを取得します。|  
|[accelerator::description データ メンバー](#accelerator__description_data_member)|`accelerator` デバイスの短い説明を取得します。|  
|[accelerator::device_path データ メンバー](#accelerator__device_path_data_member)|デバイスのパスを取得します。|  
|[accelerator::direct3d_ref データ メンバー](#accelerator__direct3d_ref_data_member)|Direct3D 参照 `accelerator` の文字列定数を取得します。|  
|[accelerator::direct3d_warp データ メンバー](#accelerator__direct3d_warp_data_member)|文字列の定数を取得、 [アクセラレータ](../../../parallel/amp/reference/accelerator-class.md) Streaming SIMD Extensions (SSE) を使用するマルチコア Cpu で C++ AMP コードの実行に使用できるオブジェクトします。|  
|[accelerator::has_display データ メンバー](#accelerator__has_display_data_member)|`accelerator` がディスプレイにアタッチされているかどうかを示すブール値を取得します。|  
|[accelerator::is_debug データ メンバー](#accelerator__is_debug_data_member)|`accelerator` に、広範なエラー レポートに有効なデバッグ レイヤーがあるかどうかを示します。|  
|[accelerator::is_emulated データ メンバー](#accelerator__is_emulated_data_member)|`accelerator` がエミュレートされるかどうかを示します。|  
|[accelerator::supports_cpu_shared_memory データ メンバー](#accelerator__supports_cpu_shared_memory_data_member)|`accelerator` が共有メモリをサポートするかどうかを示します。|  
|[accelerator::supports_double_precision データ メンバー](#accelerator__supports_double_precision_data_member)|アクセラレータが倍精度数値演算をサポートするかどうかを示します。|  
|[accelerator::supports_limited_double_precision データ メンバー](#accelerator__supports_limited_double_precision_data_member)|アクセラレータの倍精度数値演算のサポートが制限されているかどうかを示します。|  
|[accelerator::version データ メンバー](#accelerator__version_data_member)|`accelerator` のバージョンを取得します。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `accelerator`  
  
## <a name="remarks"></a>コメント  
 アクセラレータは、データ並列計算用に最適化されたハードウェアの機能です。 多くの場合、アクセラレータは独立した GPU ですが、DirectX REF デバイス、WARP (SSE 命令で加速される CPU 側のデバイス)、または CPU 自体などの仮想ホスト側のエンティティでもあることがあります。  
  
 使用できるデバイスをエミュレートすることによって、または既定のデバイス、参照デバイス、または WARP デバイスを取得することによって、`accelerator` オブジェクトを構築することができます。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** amprt.h  
  
 **名前空間:** Concurrency  
  
##  <a name="a-nameacceleratordtoracceleratordestructora-acceleratoraccelerator-destructor"></a><a name="accelerator___dtoraccelerator_destructor"></a>  accelerator:: ~ accelerator デストラクター  
 破棄、 [アクセラレータ](../../../parallel/amp/reference/accelerator-class.md) オブジェクトです。  
  
```  
~accelerator();
```  
  
### <a name="return-value"></a>戻り値  
  
##  <a name="a-nameacceleratoracceleratorconstructora-acceleratoraccelerator-constructor"></a><a name="accelerator__accelerator_constructor"></a>  accelerator::accelerator コンス トラクター  
 新しいインスタンスを初期化、 [accelerator クラス](../../../parallel/amp/reference/accelerator-class.md)します。  
  
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
  
##  <a name="a-nameacceleratorcpuacceleratordatamembera-acceleratorcpuaccelerator-data-member"></a><a name="accelerator__cpu_accelerator_data_member"></a>  accelerator::cpu_accelerator データ メンバー  
 CPU アクセラレータの文字列定数を取得します。  
  
```  
static const wchar_t cpu_accelerator[];  
```  
  
##  <a name="a-nameacceleratorcreateviewmethoda-acceleratorcreateview-method"></a><a name="accelerator__create_view_method"></a>  accelerator::create_view メソッド  
 作成して返します、 `accelerator_view` 指定されたキュー モードを使用して、このアクセラレータでのオブジェクト。 キュー モードが指定されていない場合、新しい `accelerator_view` を使用して、 [queuing_mode::immediate](../Topic/concurrency%20namespace%20enums.md#queuing_mode) キュー モード。  
  
```  
accelerator_view create_view(queuing_mode qmode = queuing_mode_automatic);
```  
  
### <a name="parameters"></a>パラメーター  
 `qmode`  
 キュー モード。  
  
### <a name="return-value"></a>戻り値  
 新しい `accelerator_view` 指定されたキュー モードを使用して、このアクセラレータでのオブジェクト。  
  
##  <a name="a-nameacceleratordedicatedmemorydatamembera-acceleratordedicatedmemory-data-member"></a><a name="accelerator__dedicated_memory_data_member"></a>  accelerator::dedicated_memory データ メンバー  
 専用のメモリを取得、 [アクセラレータ](../../../parallel/amp/reference/accelerator-class.md), 、(キロバイト単位)。  
  
```  
__declspec(property(get= get_dedicated_memory)) size_t dedicated_memory;  
```  
  
##  <a name="a-nameacceleratordefaultacceleratordatamembera-acceleratordefaultaccelerator-data-member"></a><a name="accelerator__default_accelerator_data_member"></a>  accelerator::default_accelerator データ メンバー  
 定数文字列を既定値を取得 [アクセラレータ](../../../parallel/amp/reference/accelerator-class.md)します。  
  
```  
static const wchar_t default_accelerator[];  
```  
  
##  <a name="a-nameacceleratordefaultcpuaccesstypedatamembera-acceleratordefaultcpuaccesstype-data-member"></a><a name="accelerator__default_cpu_access_type_data_member"></a>  accelerator::default_cpu_access_type データ メンバー  
 既定の cpu [access_type](../Topic/concurrency%20namespace%20enums.md#access_type) 配列および暗黙的なメモリの割り当てに対するこの `accelerator`します。  
  
```  
__declspec(property(get= get_default_cpu_access_type)) access_type default_cpu_access_type;  
```  
  
##  <a name="a-nameacceleratordefaultviewdatamembera-acceleratordefaultview-data-member"></a><a name="accelerator__default_view_data_member"></a>  accelerator::default_view データ メンバー  
 関連付けられている既定のアクセラレータ ビューを取得、 [アクセラレータ](../../../parallel/amp/reference/accelerator-class.md)します。  
  
```  
__declspec(property(get= get_default_view)) accelerator_view default_view;  
```  
  
##  <a name="a-nameacceleratordescriptiondatamembera-acceleratordescription-data-member"></a><a name="accelerator__description_data_member"></a>  accelerator::description データ メンバー  
 短い説明を取得、 [アクセラレータ](../../../parallel/amp/reference/accelerator-class.md) デバイスです。  
  
```  
__declspec(property(get= get_description)) std::wstring description;  
```  
  
##  <a name="a-nameacceleratordevicepathdatamembera-acceleratordevicepath-data-member"></a><a name="accelerator__device_path_data_member"></a>  accelerator::device_path データ メンバー  
 アクセラレータのパスを取得します。 パスは、システム上で一意です。  
  
```  
__declspec(property(get= get_device_path)) std::wstring device_path;  
```  
  
##  <a name="a-nameacceleratordirect3drefdatamembera-acceleratordirect3dref-data-member"></a><a name="accelerator__direct3d_ref_data_member"></a>  accelerator::direct3d_ref データ メンバー  
 Direct3D 参照アクセラレータの文字列定数を取得します。  
  
```  
static const wchar_t direct3d_ref[];  
```  
  
##  <a name="a-nameacceleratordirect3dwarpdatamembera-acceleratordirect3dwarp-data-member"></a><a name="accelerator__direct3d_warp_data_member"></a>  accelerator::direct3d_warp データ メンバー  
 文字列の定数を取得、 [アクセラレータ](../../../parallel/amp/reference/accelerator-class.md) Streaming SIMD Extensions (SSE) を使用するマルチコア Cpu で C++ AMP コードの実行に使用できるオブジェクトします。  
  
```  
static const wchar_t direct3d_warp[];  
```  
  
##  <a name="a-nameacceleratorgetallmethoda-acceleratorgetall-method"></a><a name="accelerator__get_all_method"></a>  accelerator::get_all メソッド  
 使用可能なすべてのアクセラレータを表す `accelerator` オブジェクトのベクターを返します。  
  
```  
static inline std::vector<accelerator> get_all();
```  
  
### <a name="return-value"></a>戻り値  
 使用できるアクセラレータのベクター  
  
##  <a name="a-nameacceleratorgetautoselectionviewmethoda-acceleratorgetautoselectionview-method"></a><a name="accelerator__get_auto_selection_view_method"></a>  accelerator::get_auto_selection_view メソッド  
 ランタイムによって自動的に選択される parallel_for_each カーネルを実行するためにターゲットの accelerator_view で parallel_for_each ターゲット結果として指定される場合、自動選択の accelerator_view を返します。 その他のすべての目的については、このメソッドで返される accelerator_view は、既定のアクセラレータの既定の accelerator_view と同じです。  
  
```  
static accelerator_view __cdecl get_auto_selection_view();
```  
  
### <a name="return-value"></a>戻り値  
 自動選択の accelerator_view。  
  
##  <a name="a-nameacceleratorgetdedicatedmemorymethoda-acceleratorgetdedicatedmemory-method"></a><a name="accelerator__get_dedicated_memory_method"></a>  accelerator::get_dedicated_memory メソッド  
 専用のメモリを返す、 [アクセラレータ](../../../parallel/amp/reference/accelerator-class.md), 、(キロバイト単位)。  
  
```  
size_t get_dedicated_memory() const;

 
```  
  
### <a name="return-value"></a>戻り値  
 専用のメモリ、 `accelerator`, 、(キロバイト単位)。  
  
##  <a name="a-nameacceleratorgetdefaultcpuaccesstypemethoda-acceleratorgetdefaultcpuaccesstype-method"></a><a name="accelerator__get_default_cpu_access_type_method"></a>  accelerator::get_default_cpu_access_type メソッド  
 このアクセラレータで作成されるバッファーの既定の CPU access_type を取得します  
  
```  
access_type get_default_cpu_access_type() const;

 
```  
  
### <a name="return-value"></a>戻り値  
 このアクセラレータで作成されるバッファーの既定の CPU access_type。  
  
##  <a name="a-nameacceleratorgetdefaultviewmethoda-acceleratorgetdefaultview-method"></a><a name="accelerator__get_default_view_method"></a>  accelerator::get_default_view メソッド  
 既定値を返す `accelerator_view` オブジェクトに関連付けられている、 [アクセラレータ](../../../parallel/amp/reference/accelerator-class.md)します。  
  
```  
accelerator_view get_default_view() const;

 
```  
  
### <a name="return-value"></a>戻り値  
 既定値 `accelerator_view` オブジェクトに関連付けられている、 `accelerator`です。  
  
##  <a name="a-nameacceleratorgetdescriptionmethoda-acceleratorgetdescription-method"></a><a name="accelerator__get_description_method"></a>  accelerator::get_description メソッド  
 簡単な説明を返す、 [アクセラレータ](../../../parallel/amp/reference/accelerator-class.md) デバイスです。  
  
```  
std::wstring get_description() const;

 
```  
  
### <a name="return-value"></a>戻り値  
 簡単な説明、 `accelerator` デバイスです。  
  
##  <a name="a-nameacceleratorgetdevicepathmethoda-acceleratorgetdevicepath-method"></a><a name="accelerator__get_device_path_method"></a>  accelerator::get_device_path メソッド  
 アクセラレータのパスを返します。 パスは、システム上で一意です。  
  
```  
std::wstring get_device_path() const;

 
```  
  
### <a name="return-value"></a>戻り値  
 一意のデバイスをシステム全体にわたるインスタンスのパス。  
  
##  <a name="a-nameacceleratorgethasdisplaymethoda-acceleratorgethasdisplay-method"></a><a name="accelerator__get_has_display_method"></a>  accelerator::get_has_display メソッド  
 示すブール値を返すかどうか、 [アクセラレータ](../../../parallel/amp/reference/accelerator-class.md) ディスプレイに出力できます。  
  
```  
bool get_has_display() const;

 
```  
  
### <a name="return-value"></a>戻り値  
 `true` がディスプレイに出力できる場合は `accelerator`。それ以外の場合は `false`。  
  
##  <a name="a-nameacceleratorgetisdebugmethoda-acceleratorgetisdebug-method"></a><a name="accelerator__get_is_debug_method"></a>  accelerator::get_is_debug メソッド  
 指定するかどうか、 [アクセラレータ](../../../parallel/amp/reference/accelerator-class.md) 広範なエラー レポートに有効なデバッグ レイヤーを持ちます。  
  
```  
bool get_is_debug() const;

 
```  
  
### <a name="return-value"></a>戻り値  
 `true` に、広範なエラー レポートに有効なデバッグ レイヤーがある場合、`accelerator`。 それ以外の場合は `false`。  
  
##  <a name="a-nameacceleratorgetisemulatedmethoda-acceleratorgetisemulated-method"></a><a name="accelerator__get_is_emulated_method"></a>  accelerator::get_is_emulated メソッド  
 指定するかどうか、 [アクセラレータ](../../../parallel/amp/reference/accelerator-class.md) がエミュレートされます。  
  
```  
bool get_is_emulated() const;

 
```  
  
### <a name="return-value"></a>戻り値  
 `true` がエミュレートされる場合、`accelerator`。 それ以外の場合は `false`。  
  
##  <a name="a-nameacceleratorgetsupportscpusharedmemorymethoda-acceleratorgetsupportscpusharedmemory-method"></a><a name="accelerator__get_supports_cpu_shared_memory_method"></a>  accelerator::get_supports_cpu_shared_memory メソッド  
 アクセラレータがアクセラレータと CPU の両方からアクセスできるメモリをサポートするかどうかを示すブール値を返します。  
  
```  
bool get_supports_cpu_shared_memory() const;

 
```  
  
### <a name="return-value"></a>戻り値  
 アクセラレータが CPU 共有メモリをサポートする場合は `true`、それ以外の場合は `false`。  
  
##  <a name="a-nameacceleratorgetsupportsdoubleprecisionmethoda-acceleratorgetsupportsdoubleprecision-method"></a><a name="accelerator__get_supports_double_precision_method"></a>  accelerator::get_supports_double_precision メソッド  
 アクセラレータが融合型積和演算 (FMA)、除算、逆数、および `int` と `double` 間のキャストなどの倍精度演算をサポートするかどうかを示すブール値を返します。  
  
```  
bool get_supports_double_precision() const;

 
```  
  
### <a name="return-value"></a>戻り値  
 アクセラレータが倍精度演算をサポートする場合は `true`、それ以外の場合は `false`。  
  
##  <a name="a-nameacceleratorgetsupportslimiteddoubleprecisionmethoda-acceleratorgetsupportslimiteddoubleprecision-method"></a><a name="accelerator__get_supports_limited_double_precision_method"></a>  accelerator::get_supports_limited_double_precision メソッド  
 アクセラレータが倍精度演算のサポートを制限されているかどうかを示すブール値を返します。 アクセラレータが一部のみがサポート、乗算定着し、追加 (FMA)、除算、逆数、および間のキャスト `int` と `double` はサポートされていません。  
  
```  
bool get_supports_limited_double_precision() const;

 
```  
  
### <a name="return-value"></a>戻り値  
 `true` アクセラレータの倍精度演算; のサポートが制限されている場合それ以外の場合、 `false`です。  
  
##  <a name="a-nameacceleratorgetversionmethoda-acceleratorgetversion-method"></a><a name="accelerator__get_version_method"></a>  accelerator::get_version メソッド  
 バージョンを返す、 [アクセラレータ](../../../parallel/amp/reference/accelerator-class.md)します。  
  
```  
unsigned int get_version() const;

 
```  
  
### <a name="return-value"></a>戻り値  
 バージョン、 `accelerator`です。  
  
##  <a name="a-nameacceleratorhasdisplaydatamembera-acceleratorhasdisplay-data-member"></a><a name="accelerator__has_display_data_member"></a>  accelerator::has_display データ メンバー  
 示すブール値を取得するかどうか、 [アクセラレータ](../../../parallel/amp/reference/accelerator-class.md) ディスプレイに出力できます。  
  
```  
__declspec(property(get= get_has_display)) bool has_display;  
```  
  
##  <a name="a-nameacceleratorisdebugdatamembera-acceleratorisdebug-data-member"></a><a name="accelerator__is_debug_data_member"></a>  accelerator::is_debug データ メンバー  
 示すブール値を取得するかどうか、 [アクセラレータ](../../../parallel/amp/reference/accelerator-class.md) 広範なエラー レポートに有効なデバッグ レイヤーを持ちます。  
  
```  
__declspec(property(get= get_is_debug)) bool is_debug;  
```  
  
##  <a name="a-nameacceleratorisemulateddatamembera-acceleratorisemulated-data-member"></a><a name="accelerator__is_emulated_data_member"></a>  accelerator::is_emulated データ メンバー  
 示すブール値を取得するかどうか、 [アクセラレータ](../../../parallel/amp/reference/accelerator-class.md) がエミュレートされます。  
  
```  
__declspec(property(get= get_is_emulated)) bool is_emulated;  
```  
  
##  <a name="a-nameacceleratoroperatorneqoperatora-acceleratoroperator-operator"></a><a name="accelerator__operator_neq_operator"></a>  accelerator::operator! = 演算子  
 この `accelerator` オブジェクトを別のオブジェクトと比較し、同じ場合は `false` を返し、それ以外の場合は `true` を返します。  
  
```  
bool operator!= (const accelerator& _Other) const;

 
```  
  
### <a name="parameters"></a>パラメーター  
 `_Other`  
  `accelerator` これと比較するオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 `false` 場合は、2 つ `accelerator` オブジェクトが等しい。 そうしないと、 `true`です。  
  
##  <a name="a-nameacceleratoroperatoreqoperatora-acceleratoroperator-operator"></a><a name="accelerator__operator_eq_operator"></a>  accelerator::operator = 演算子  
 指定した内容をコピー [アクセラレータ](../../../parallel/amp/reference/accelerator-class.md) オブジェクトをこのオブジェクトにします。  
  
```  
accelerator& operator= (const accelerator& _Other);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Other`  
 コピー元の `accelerator` オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 この `accelerator` オブジェクトへの参照。  
  
##  <a name="a-nameacceleratoroperatoreqeqoperatora-acceleratoroperator-operator"></a><a name="accelerator__operator_eq_eq_operator"></a>  accelerator::operator = 演算子  
 この比較 [アクセラレータ](../../../parallel/amp/reference/accelerator-class.md) と他のオブジェクトを返します `true` は同じである場合、それ以外の場合を返します `false`します。  
  
```  
bool operator== (const accelerator& _Other) const;

 
```  
  
### <a name="parameters"></a>パラメーター  
 `_Other`  
  `accelerator` これと比較するオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 `true` 場合、その他の `accelerator` オブジェクトはこれと同じ `accelerator` オブジェクト。 それ以外の場合、 `false`です。  
  
##  <a name="a-nameacceleratorsetdefaultmethoda-acceleratorsetdefault-method"></a><a name="accelerator__set_default_method"></a>  accelerator::set_default メソッド  
 暗黙的に既定のアクセラレータを使用するすべての操作に使用する既定のアクセラレータを設定します。 このメソッドは、ランタイムによって選択された既定のアクセラレータが暗黙的に既定のアクセラレータを使用する操作で既に使用されていない場合にのみ正常に終了します  
  
```  
static inline bool set_default(std::wstring _Path);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Path`  
 アクセラレータへのパス。  
  
### <a name="return-value"></a>戻り値  
 既定のアクセラレータの設定で呼び出しが成功した場合、`true`。 それ以外の場合は `false`。  
  
##  <a name="a-nameacceleratorsetdefaultcpuaccesstypemethoda-acceleratorsetdefaultcpuaccesstype-method"></a><a name="accelerator__set_default_cpu_access_type_method"></a>  accelerator::set_default_cpu_access_type メソッド  
 このアクセラレータで作成される配列、またはこのアクセラレータでアクセスされる array_views の一部としての暗黙的なメモリ割り当てに、既定の CPU access_type を設定します。 アクセラレータの default_cpu_access_type がこのメソッドへの前の呼び出しによってまだオーバーライドされておらず、このアクセラレータのために default_cpu_access_type を選択したランタイムが、配列の割り当てまたはこのアクセラレータでアクセスされる array_view の暗黙的なメモリ割り当てバッキングにまだ使用されていない場合にのみ、このメソッドは成功します。  
  
```  
bool set_default_cpu_access_type(access_type _Default_cpu_access_type);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Default_cpu_access_type`  
 このアクセラレータの array/array_view メモリ割り当てに使用される既定の CPU access_type。  
  
### <a name="return-value"></a>戻り値  
 アクセラレータの既定の CPU access_type が正常に設定されたかどうかを示すブール値。  
  
##  <a name="a-nameacceleratorsupportscpusharedmemorydatamembera-acceleratorsupportscpusharedmemory-data-member"></a><a name="accelerator__supports_cpu_shared_memory_data_member"></a>  accelerator::supports_cpu_shared_memory データ メンバー  
 `accelerator` が共有メモリをサポートしているかどうか示すブール値を取得します。  
  
```  
__declspec(property(get= get_supports_cpu_shared_memory)) bool supports_cpu_shared_memory;  
```  
  
##  <a name="a-nameacceleratorsupportsdoubleprecisiondatamembera-acceleratorsupportsdoubleprecision-data-member"></a><a name="accelerator__supports_double_precision_data_member"></a>  accelerator::supports_double_precision データ メンバー  
 アクセラレータが倍精度浮動小数点演算をサポートするかどうかを示すブール値を取得します。  
  
```  
__declspec(property(get= get_supports_double_precision)) bool supports_double_precision;  
```  
  
##  <a name="a-nameacceleratorsupportslimiteddoubleprecisiondatamembera-acceleratorsupportslimiteddoubleprecision-data-member"></a><a name="accelerator__supports_limited_double_precision_data_member"></a>  accelerator::supports_limited_double_precision データ メンバー  
 アクセラレータが倍精度演算のサポートを制限されているかどうかを示すブール値を取得します。 アクセラレータが一部のみがサポート、乗算定着し、追加 (FMA)、除算、逆数、および間のキャスト `int` と `double` はサポートされていません。  
  
```  
__declspec(property(get= get_supports_limited_double_precision)) bool supports_limited_double_precision;  
```  
  
##  <a name="a-nameacceleratorversiondatamembera-acceleratorversion-data-member"></a><a name="accelerator__version_data_member"></a>  accelerator::version データ メンバー  
 バージョンを取得、 [アクセラレータ](../../../parallel/amp/reference/accelerator-class.md)します。  
  
```  
__declspec(property(get= get_version)) unsigned int version;  
```  
  
##  <a name="a-nameacceleratorviewdtoracceleratorviewdestructora-acceleratorviewacceleratorview-destructor"></a><a name="accelerator_view___dtoraccelerator_view_destructor"></a>  accelerator_view:: ~ accelerator_view デストラクター  
 破棄、 [accelerator_view](../Topic/accelerator_view%20Class.md) オブジェクトです。  
  
```  
~accelerator_view();
```  
  
### <a name="return-value"></a>戻り値  
  
##  <a name="a-nameacceleratorviewacceleratordatamembera-acceleratorviewaccelerator-data-member"></a><a name="accelerator_view__accelerator_data_member"></a>  accelerator_view::accelerator データ メンバー  
 取得、 [アクセラレータ](../../../parallel/amp/reference/accelerator-class.md) のオブジェクト、 [accelerator_view](../Topic/accelerator_view%20Class.md) オブジェクトです。  
  
```  
__declspec(property(get= get_accelerator)) Concurrency::accelerator accelerator;  
```  
  
##  <a name="a-nameacceleratorviewacceleratorviewconstructora-acceleratorviewacceleratorview-constructor"></a><a name="accelerator_view__accelerator_view_constructor"></a>  accelerator_view::accelerator_view コンス トラクター  
 新しいインスタンスを初期化、 [accelerator_view](../Topic/accelerator_view%20Class.md) クラス、既存のコピーを `accelerator_view` オブジェクトです。  
  
```  
accelerator_view(const accelerator_view& _Other);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Other`  
 コピーする `accelerator_view` オブジェクト。  
  
##  <a name="a-nameacceleratorviewcreatemarkermethoda-acceleratorviewcreatemarker-method"></a><a name="accelerator_view__create_marker_method"></a>  accelerator_view::create_marker メソッド  
 これまでにこの `accelerator_view` オブジェクトに送信されたすべてのコマンドの完了を追跡するために予定を返します。  
  
```  
concurrency::completion_future create_marker();
```  
  
### <a name="return-value"></a>戻り値  
 これまでこの `accelerator_view` オブジェクトに送信されたすべてのコマンドの完了を追跡するための予定です。  
  
##  <a name="a-nameacceleratorviewflushmethoda-acceleratorviewflush-method"></a><a name="accelerator_view__flush_method"></a>  accelerator_view::flush メソッド  
 キューに格納されたすべての保留中のコマンドを送信する、 [accelerator_view](../Topic/accelerator_view%20Class.md) 実行するためのアクセラレータへのオブジェクト。  
  
```  
void flush();
```  
  
### <a name="return-value"></a>戻り値  
 `void` を返します。  
  
##  <a name="a-nameacceleratorviewgetacceleratormethoda-acceleratorviewgetaccelerator-method"></a><a name="accelerator_view__get_accelerator_method"></a>  accelerator_view::get_accelerator メソッド  
 返します。、 [アクセラレータ](../../../parallel/amp/reference/accelerator-class.md) のオブジェクト、 [accelerator_view](../Topic/accelerator_view%20Class.md) オブジェクトです。  
  
```  
accelerator get_accelerator() const;

 
```  
  
### <a name="return-value"></a>戻り値  
  `accelerator` のオブジェクト、 `accelerator_view` オブジェクトです。  
  
##  <a name="a-nameacceleratorviewgetisautoselectionmethoda-acceleratorviewgetisautoselection-method"></a><a name="accelerator_view__get_is_auto_selection_method"></a>  accelerator_view::get_is_auto_selection メソッド  
 選択を示すかどうか、ランタイムは自動的に適切なアクセラレータ accelerator_view に渡されるブール値を返す、 [parallel_for_each](../Topic/concurrency%20namespace%20functions.md#parallel_for_each)します。  
  
```  
bool get_is_auto_selection() const;

 
```  
  
### <a name="return-value"></a>戻り値  
 ランタイムが自動的に適切なアクセラレータを選択する場合は `true`、それ以外の場合は `false`。  
  
##  <a name="a-nameacceleratorviewgetisdebugmethoda-acceleratorviewgetisdebug-method"></a><a name="accelerator_view__get_is_debug_method"></a>  accelerator_view::get_is_debug メソッド  
 示すブール値を返すかどうか、 [accelerator_view](../Topic/accelerator_view%20Class.md) 広範なエラー レポートに有効なデバッグ レイヤーが付きます。  
  
```  
bool get_is_debug() const;

 
```  
  
### <a name="return-value"></a>戻り値  
 示すブール値かどうか、 `accelerator_view` 広範なエラー レポートに有効なデバッグ レイヤーが付きます。  
  
##  <a name="a-nameacceleratorviewgetqueuingmodemethoda-acceleratorviewgetqueuingmode-method"></a><a name="accelerator_view__get_queuing_mode_method"></a>  accelerator_view::get_queuing_mode メソッド  
 キュー モードを返す、 [accelerator_view](../Topic/accelerator_view%20Class.md) オブジェクトです。  
  
```  
queuing_mode get_queuing_mode() const;

 
```  
  
### <a name="return-value"></a>戻り値  
 キュー モード、 `accelerator_view` オブジェクトです。  
  
##  <a name="a-nameacceleratorviewgetversionmethoda-acceleratorviewgetversion-method"></a><a name="accelerator_view__get_version_method"></a>  accelerator_view::get_version メソッド  
 バージョンを返す、 [accelerator_view](../Topic/accelerator_view%20Class.md)します。  
  
```  
unsigned int get_version() const;

 
```  
  
### <a name="return-value"></a>戻り値  
 バージョン、 `accelerator_view`です。  
  
##  <a name="a-nameacceleratorviewisautoselectiondatamembera-acceleratorviewisautoselection-data-member"></a><a name="accelerator_view__is_auto_selection_data_member"></a>  accelerator_view::is_auto_selection データ メンバー  
 選択を示すかどうか、ランタイムは自動的に適切なアクセラレータ accelerator_view に渡されるブール値を取得、 [parallel_for_each](concurrency%20namespace%20functions.md#parallel_for_each)します。  
  
```  
__declspec(property(get= get_is_auto_selection)) bool is_auto_selection;  
```  
  
##  <a name="a-nameacceleratorviewisdebugdatamembera-acceleratorviewisdebug-data-member"></a><a name="accelerator_view__is_debug_data_member"></a>  accelerator_view::is_debug データ メンバー  
 示すブール値を取得するかどうか、 [accelerator_view](../Topic/accelerator_view%20Class.md) 広範なエラー レポートに有効なデバッグ レイヤーが付きます。  
  
```  
__declspec(property(get= get_is_debug)) bool is_debug;  
```  
  
##  <a name="a-nameacceleratorviewoperatorneqoperatora-acceleratorviewoperator-operator"></a><a name="accelerator_view__operator_neq_operator"></a>  accelerator_view::operator! = 演算子  
 この比較 [accelerator_view](../Topic/accelerator_view%20Class.md) と他のオブジェクトを返します `false` は同じである場合、それ以外の場合を返します `true`します。  
  
```  
bool operator!= (const accelerator_view& _Other) const;

 
```  
  
### <a name="parameters"></a>パラメーター  
 `_Other`  
  `accelerator_view` これと比較するオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 2 つのオブジェクトが同一である場合は `false`。それ以外の場合は `true`。  
  
##  <a name="a-nameacceleratorviewoperatoreqoperatora-acceleratorviewoperator-operator"></a><a name="accelerator_view__operator_eq_operator"></a>  accelerator_view::operator = 演算子  
 指定した内容をコピー [accelerator_view](../Topic/accelerator_view%20Class.md) をこのオブジェクトです。  
  
```  
accelerator_view& operator= (const accelerator_view& _Other);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Other`  
 コピー元の `accelerator_view` オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 変更したへの参照を `accelerator_view` オブジェクトです。  
  
##  <a name="a-nameacceleratorviewoperatoreqeqoperatora-acceleratorviewoperator-operator"></a><a name="accelerator_view__operator_eq_eq_operator"></a>  accelerator_view::operator = 演算子  
 この比較 [accelerator_view](../Topic/accelerator_view%20Class.md) と他のオブジェクトを返します `true` は同じである場合、それ以外の場合を返します `false`します。  
  
```  
bool operator== (const accelerator_view& _Other) const;

 
```  
  
### <a name="parameters"></a>パラメーター  
 `_Other`  
  `accelerator_view` これと比較するオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 2 つのオブジェクトが同一である場合は `true`。それ以外の場合は `false`。  
  
##  <a name="a-nameacceleratorviewqueuingmodedatamembera-acceleratorviewqueuingmode-data-member"></a><a name="accelerator_view__queuing_mode_data_member"></a>  accelerator_view::queuing_mode データ メンバー  
 キュー モードを取得、 [accelerator_view](../Topic/accelerator_view%20Class.md) オブジェクトです。  
  
```  
__declspec(property(get= get_queuing_mode)) Concurrency::queuing_mode queuing_mode;  
```  
  
##  <a name="a-nameacceleratorviewversiondatamembera-acceleratorviewversion-data-member"></a><a name="accelerator_view__version_data_member"></a>  accelerator_view::version データ メンバー  
 バージョンを取得、 [accelerator_view](../Topic/accelerator_view%20Class.md)します。  
  
```  
__declspec(property(get= get_version)) unsigned int version;  
```  
  
##  <a name="a-nameacceleratorviewwaitmethoda-acceleratorviewwait-method"></a><a name="accelerator_view__wait_method"></a>  accelerator_view::wait メソッド  
 送信されたすべてのコマンドの待機、 [accelerator_view](../Topic/accelerator_view%20Class.md) を完了するオブジェクト。  
  
```  
void wait();
```  
  
### <a name="return-value"></a>戻り値  
 `void` を返します。  
  
## <a name="see-also"></a>関連項目  
 [Concurrency 名前空間 (C++ AMP)](../../../parallel/amp/reference/concurrency-namespace-cpp-amp.md)
