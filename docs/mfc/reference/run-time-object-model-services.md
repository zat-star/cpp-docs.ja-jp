---
title: "ランタイム オブジェクト モデル サービス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros
dev_langs:
- C++
helpviewer_keywords:
- run-time object model services macros
ms.assetid: 4a3e79df-2ee3-43a4-8193-20298828de85
caps.latest.revision: 15
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
ms.sourcegitcommit: 3d045736f9a54d344c67e3f7408198e65a0bc95f
ms.openlocfilehash: 0cc29b21aa2279e51ba666d7447d913c4cc777d4
ms.lasthandoff: 03/29/2017

---
# <a name="run-time-object-model-services"></a>ランタイム オブジェクト モデル サービス
クラスは、 [CObject](../../mfc/reference/cobject-class.md)と[CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)ランタイム クラス情報、シリアル化、および動的なオブジェクトの作成へのアクセスなど、いくつかのオブジェクトのサービスをカプセル化します。 すべてのクラスから派生した`CObject`この機能を継承します。  
  
 ランタイム クラス情報へのアクセスには、実行時に、オブジェクトのクラスに関する情報を確認することができます。 実行時にオブジェクトのクラスを判断する機能は、余分な型チェック関数の引数を使用して、オブジェクトのクラスに基づく特殊なコードを記述する必要がありますが必要なときに便利です。 ランタイム クラス情報は、C++ 言語によって直接サポートされていません。  
  
 シリアル化は、ファイルからの書き込みまたはオブジェクトの内容を読み取り中のプロセスです。 シリアル化を使用して、アプリケーションの終了後も、オブジェクトの内容を保存することができます。 アプリケーションを再起動すると、オブジェクトは、ファイルから読み取ることができます。 このようなデータ オブジェクトと呼ばれます「固定」です。  
  
 動的オブジェクトの作成では、実行時に指定したクラスのオブジェクトを作成することができます。 たとえば、ドキュメント、ビュー、およびフレーム オブジェクト必要があります作成をサポート動的フレームワークは、それらを動的に作成する必要があるためです。  
  
 次の表は、ランタイム クラス情報、シリアル化、および動的な作成をサポートする MFC マクロを一覧表示します。  
  
 これらの実行時のオブジェクトのサービスとシリアル化の詳細については、記事を参照してください。 [CObject クラス: クラス情報にアクセスする](../../mfc/accessing-run-time-class-information.md)です。  
  
### <a name="run-time-object-model-services-macros"></a>ランタイム オブジェクト モデル サービス マクロ  
  
|||  
|-|-|  
|[DECLARE_DYNAMIC](#declare_dynamic)|(クラス宣言で使用する必要があります)、ランタイム クラス情報にアクセスできます。|  
|[DECLARE_DYNCREATE](#declare_dyncreate)|動的に作成し (クラス宣言で使用する必要があります)、ランタイム クラス情報へのアクセスを有効にします。|  
|[DECLARE_SERIAL](#declare_serial)|シリアル化および (クラス宣言で使用する必要があります)、ランタイム クラス情報へのアクセスを有効にします。|  
|[新規クラス](#implement_dynamic)|(クラスの実装で使用する必要があります)、ランタイム クラス情報にアクセスできます。|  
|[IMPLEMENT_DYNCREATE](#implement_dyncreate)|動的な作成と実行時の情報 (クラスの実装で使用する必要があります) へのアクセスを有効にします。|  
|[IMPLEMENT_SERIAL](#implement_serial)|シリアル化および (クラスの実装で使用する必要があります)、ランタイム クラス情報へのアクセスを許可します。|  
|[RUNTIME_CLASS](#runtime_class)|返します、`CRuntimeClass`名前付きのクラスに対応する構造体。|  


 OLE には、頻繁に実行時にオブジェクトの動的作成が必要です。 たとえば、OLE サーバー アプリケーションは、クライアントからの要求に対する応答で OLE 項目を動的に作成できる必要があります。 同様に、オートメーション サーバーは、オートメーション クライアントからの要求に応答で項目を作成できる必要があります。  
  
 Microsoft Foundation Class ライブラリでは、OLE に特定の 2 つのマクロを提供します。  
  
### <a name="dynamic-creation-of-ole-objects"></a>OLE オブジェクトの動的生成  
  
|||  
|-|-|  
|[DECLARE_OLECREATE](#declare_olecreate)|OLE オートメーションを通じて作成されるオブジェクトを有効にします。|  
|[IMPLEMENT_OLECREATE](#implement_olecreate)|OLE システムによって作成されるオブジェクトを有効にします。|  
  
##  <a name="declare_dynamic"></a>DECLARE_DYNAMIC  
 クラスを派生している場合、オブジェクトのクラスに関する実行時情報にアクセスする機能が追加`CObject`です。  
  
```
DECLARE_DYNAMIC(class_name) 
```  
  
### <a name="parameters"></a>パラメーター  
 *それ以外*  
 クラスの実際の名前。  
  
### <a name="remarks"></a>コメント  
 追加、`DECLARE_DYNAMIC`クラスのヘッダー (.h) モジュールにマクロをこのクラスのオブジェクトへのアクセスを必要とするすべての .cpp モジュールにし、そのモジュールを含めます。  
  
 使用する場合、 **DECLARE**_**ダイナミック**と`IMPLEMENT_DYNAMIC`マクロの説明に従って、行うこともできますし、`RUNTIME_CLASS`マクロと`CObject::IsKindOf`実行時に、オブジェクトのクラスを判断する関数。  
  
 場合`DECLARE_DYNAMIC`し、クラス宣言に含まれる`IMPLEMENT_DYNAMIC`クラスの実装に含める必要があります。  
  
 詳細については、`DECLARE_DYNAMIC`マクロを参照してください[CObject クラスのトピック](../../mfc/using-cobject.md)です。  
  
### <a name="example"></a>例  
 例を参照して[IMPLEMENT_DYNAMIC](#implement_dynamic)です。  

### <a name="requirements"></a>要件  
 **ヘッダー:** afx.h 

##  <a name="declare_dyncreate"></a>DECLARE_DYNCREATE  
 オブジェクト`CObject`-実行時に動的に作成するクラスを派生します。  
  
```
DECLARE_DYNCREATE(class_name)   
```  
  
### <a name="parameters"></a>パラメーター  
 *それ以外*  
 クラスの実際の名前。  
  
### <a name="remarks"></a>コメント  
 フレームワークでは、この機能を使用して、新しいオブジェクトを動的に作成します。 たとえば、新しいビュー、新しいドキュメントを開くときに作成します。 ドキュメント、ビュー、およびフレーム クラスは、フレームワークは、それらを動的に作成する必要があるための動的生成をサポートする必要があります。  
  
 追加、`DECLARE_DYNCREATE`マクロでは、.h モジュール、クラスをモジュールに含めるをこのクラスのオブジェクトへのアクセスを必要とするすべての .cpp モジュール。  
  
 場合`DECLARE_DYNCREATE`し、クラス宣言に含まれる`IMPLEMENT_DYNCREATE`クラスの実装に含める必要があります。  
  
 詳細については、`DECLARE_DYNCREATE`マクロを参照してください[CObject クラスのトピック](../../mfc/using-cobject.md)です。  
  
> [!NOTE]
>  `DECLARE_DYNCREATE`マクロには、すべての機能が含まれている`DECLARE_DYNAMIC`です。  
  
### <a name="example"></a>例  
 例を参照して[IMPLEMENT_DYNCREATE](#implement_dyncreate)です。  

### <a name="requirements"></a>要件  
 **ヘッダー:** afx.h 

##  <a name="declare_serial"></a>DECLARE_SERIAL  
 コードを生成、C++ ヘッダーに必要な`CObject`のシリアル化できるクラスを派生します。  
  
```
DECLARE_SERIAL(class_name)   
```  
  
### <a name="parameters"></a>パラメーター  
 *それ以外*  
 クラスの実際の名前。  
  
### <a name="remarks"></a>コメント  
 シリアル化は、書き込み、またはオブジェクトの内容を読み取るファイルからのプロセスです。  
  
 使用して、`DECLARE_SERIAL`モジュールでは、.h、マクロをこのクラスのオブジェクトへのアクセスを必要とするすべての .cpp モジュールにそのモジュールを含めるとします。  
  
 場合`DECLARE_SERIAL`し、クラス宣言に含まれる`IMPLEMENT_SERIAL`クラスの実装に含める必要があります。  
  
 `DECLARE_SERIAL`マクロには、すべての機能が含まれている`DECLARE_DYNAMIC`と`DECLARE_DYNCREATE`です。  
  
 使用することができます、 **AFX_API**マクロで自動的にエクスポート、`CArchive`抽出演算子のクラスを使用する、`DECLARE_SERIAL`と`IMPLEMENT_SERIAL`マクロです。 次のコードをクラス宣言 (.h ファイルにあります) を角かっこには。  
  
 [!code-cpp[NVC_MFCCObjectSample #20](../../mfc/codesnippet/cpp/run-time-object-model-services_1.h)]  
  
 詳細については、`DECLARE_SERIAL`マクロを参照してください[CObject クラスのトピック](../../mfc/using-cobject.md)です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCObjectSample # 21](../../mfc/codesnippet/cpp/run-time-object-model-services_2.h)]  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** afx.h 

##  <a name="implement_dynamic"></a>新規クラス  
 動的なのために必要な C++ コードを生成`CObject`-クラス名と、階層内の位置に実行時アクセス権を持つクラスを派生します。  
  
```
IMPLEMENT_DYNAMIC(class_name, base_class_name)  
```  
  
### <a name="parameters"></a>パラメーター  
 *それ以外*  
 クラスの実際の名前。  
  
 `base_class_name`  
 基本クラスの名前。  
  
### <a name="remarks"></a>コメント  
 使用して、`IMPLEMENT_DYNAMIC`マクロで、.cpp モジュール、および、リンク、結果のオブジェクト コードの 1 回だけです。  
  
 詳細については、次を参照してください。 [CObject クラスのトピック](../../mfc/using-cobject.md)です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCObjectSample #2](../../mfc/codesnippet/cpp/run-time-object-model-services_3.h)]  
  
 [!code-cpp[NVC_MFCCObjectSample #3](../../mfc/codesnippet/cpp/run-time-object-model-services_4.cpp)]  

### <a name="requirements"></a>要件  
 **ヘッダー:** afx.h 

##  <a name="implement_dyncreate"></a>IMPLEMENT_DYNCREATE  
 オブジェクト`CObject`-実行時に動的に作成するクラスを派生と共に使用すると、`DECLARE_DYNCREATE`マクロです。  
  
```
IMPLEMENT_DYNCREATE(class_name, base_class_name)   
```  
  
### <a name="parameters"></a>パラメーター  
 *それ以外*  
 クラスの実際の名前。  
  
 `base_class_name`  
 基本クラスの実際の名前。  
  
### <a name="remarks"></a>コメント  
 フレームワークでは、この機能を使用して、新しいオブジェクトを動的に作成、たとえば、オブジェクトをシリアル化中にディスクから読み込むときにします。 追加、`IMPLEMENT_DYNCREATE`クラス実装ファイル内のマクロです。 詳細については、次を参照してください。 [CObject クラスのトピック](../../mfc/using-cobject.md)です。  
  
 使用する場合、`DECLARE_DYNCREATE`と`IMPLEMENT_DYNCREATE`マクロを使用して、`RUNTIME_CLASS`マクロと`CObject::IsKindOf`メンバー関数を実行時に、オブジェクトのクラスを決定します。  
  
 場合`DECLARE_DYNCREATE`し、クラス宣言に含まれる`IMPLEMENT_DYNCREATE`クラスの実装に含める必要があります。  
  
 このマクロ定義が、クラスの既定のコンス トラクターを呼び出すことに注意してください。 非自明なコンス トラクターが明示的に実装されている場合、クラス、既定のコンス トラクターも明示的に実装する必要があります。 クラスの既定のコンス トラクターを追加することができます**プライベート**または**保護**メンバーのセクションでは、クラスの実装の外部から呼び出されるようにします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCObjectSample # 22](../../mfc/codesnippet/cpp/run-time-object-model-services_5.h)]  
  
 [!code-cpp[NVC_MFCCObjectSample # 23](../../mfc/codesnippet/cpp/run-time-object-model-services_6.cpp)]  

### <a name="requirements"></a>要件  
 **ヘッダー:** afx.h 

##  <a name="implement_serial"></a>IMPLEMENT_SERIAL  
 動的なのために必要な C++ コードを生成`CObject`-クラス名と、階層内の位置に実行時アクセス権を持つクラスを派生します。  
  
```
IMPLEMENT_SERIAL(class_name, base_class_name, wSchema)  
```  
  
### <a name="parameters"></a>パラメーター  
 *それ以外*  
 クラスの実際の名前。  
  
 `base_class_name`  
 基本クラスの名前。  
  
 *wSchema*  
 A **UINT**を逆シリアル化のプログラムを特定し、作成したデータの処理を有効にする、アーカイブにエンコードされる「バージョン番号」以前のバージョンのプログラムです。 クラスのスキーマの番号では、-1 をすることはできません。  
  
### <a name="remarks"></a>コメント  
 使用して、`IMPLEMENT_SERIAL`マクロ .cpp モジュールで 1 回だけ作成されるオブジェクト コードをリンクします。  
  
 使用することができます、 **AFX_API**マクロで自動的にエクスポート、`CArchive`抽出演算子のクラスを使用する、`DECLARE_SERIAL`と`IMPLEMENT_SERIAL`マクロです。 次のコードをクラス宣言 (.h ファイルにあります) を角かっこには。  
  
 [!code-cpp[NVC_MFCCObjectSample #20](../../mfc/codesnippet/cpp/run-time-object-model-services_1.h)]  
  
 詳細については、次を参照してください。、 [CObject クラスのトピック](../../mfc/using-cobject.md)です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCObjectSample # 24](../../mfc/codesnippet/cpp/run-time-object-model-services_7.cpp)]  

### <a name="requirements"></a>要件  
 **ヘッダー:** afx.h 

##  <a name="runtime_class"></a>RUNTIME_CLASS  
 C++ のクラスの名前から、実行時のクラス構造体を取得します。  
  
```
RUNTIME_CLASS(class_name)  
```  
  
### <a name="parameters"></a>パラメーター  
 *それ以外*  
 (引用符で囲まれていない) クラスの実際の名前。  
  
### <a name="remarks"></a>コメント  
 `RUNTIME_CLASS`ポインターを返します、 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)で指定されたクラスの構造体*class_name*です。 のみ`CObject`-派生クラスで宣言された`DECLARE_DYNAMIC`、 `DECLARE_DYNCREATE`、または`DECLARE_SERIAL`へのポインターを返す、`CRuntimeClass`構造体。  
  
 詳細については、次を参照してください。 [CObject クラスのトピック](../../mfc/using-cobject.md)です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCObjectSample #25](../../mfc/codesnippet/cpp/run-time-object-model-services_8.cpp)]  

### <a name="requirements"></a>要件  
 **ヘッダー:** afx.h 
   
##  <a name="declare_olecreate"></a>DECLARE_OLECREATE  
 オブジェクト`CCmdTarget`の OLE オートメーションを通じて作成されるクラスを派生します。  
  
```
DECLARE_OLECREATE(class_name) 
```  
  
### <a name="parameters"></a>パラメーター  
 *それ以外*  
 クラスの実際の名前。  
  
### <a name="remarks"></a>コメント  
 このマクロは、この型のオブジェクトを作成するその他の OLE 対応のアプリケーションを使用できます。  
  
 追加、`DECLARE_OLECREATE`クラスの .h モジュールでのマクロをこのクラスのオブジェクトへのアクセスを必要とするすべての .cpp モジュールにそのモジュールを含めるとします。  
  
 場合`DECLARE_OLECREATE`し、クラス宣言に含まれる`IMPLEMENT_OLECREATE`クラスの実装に含める必要があります。 クラスの宣言を使用して、`DECLARE_OLECREATE`も使用する必要があります`DECLARE_DYNCREATE`または`DECLARE_SERIAL`です。  

### <a name="requirements"></a>要件  
 **ヘッダー**: afxdisp.h  

##  <a name="implement_olecreate"></a>IMPLEMENT_OLECREATE  
 このいずれかのマクロまたは[IMPLEMENT_OLECREATE_FLAGS](http://msdn.microsoft.com/library/d1589f6a-5a69-4742-b07c-4c621cfd040d)が任意のクラスを使用する実装ファイル内で出現`DECLARE_OLECREATE`です。  
  
```
IMPLEMENT_OLECREATE(class_name, external_name, l, w1, w2, b1, b2, b3, b4, b5, b6, b7, b8)  
```  
  
### <a name="parameters"></a>パラメーター  
 *それ以外*  
 クラスの実際の名前。  
  
 *external_name*  
 (引用符で囲まれた) その他のアプリケーションに公開されるオブジェクトの名前。  
  
 *l*, *w1*, *w2*, *b1*, *b2*, *b3*, *b4*, *b5*, *b6*, *b7*, *b8*  
 クラスのコンポーネント**CLSID**です。  
  
### <a name="remarks"></a>コメント  
  
> [!NOTE]
>  使用する場合`IMPLEMENT_OLECREATE`既定では、1 つのスレッド モデルのみをサポートします。 使用する場合`IMPLEMENT_OLECREATE_FLAGS`を使用して、オブジェクトがサポートしているスレッド処理モデルを指定することができます、`nFlags`パラメーター。  
  
 外部名は、他のアプリケーションに公開されている識別子です。 クライアント アプリケーションでは、外部名を使用して、オートメーション サーバーからこのクラスのオブジェクトを要求します。  
  
 OLE クラス ID は、オブジェクトの一意な 128 ビット識別子です。 いずれかで構成されます**長い**、2 つ**WORD**秒、および 8**バイト**s で表される*l*、 *w1*、 *w2*、および*b1*を通じて*b8*構文の説明にします。 アプリケーション ウィザードとコードのウィザードでは、必要に応じての一意の OLE クラス Id を作成します。  

### <a name="requirements"></a>要件  
 **ヘッダー**: afxdisp.h 

## <a name="see-also"></a>関連項目  
 [マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)

