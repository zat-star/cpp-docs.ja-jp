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
ms.sourcegitcommit: 17a158366f94d27b7a46917282425d652e6b9042
ms.openlocfilehash: 8739201489644b0f1695a70d0dc12d04ca47aa68
ms.lasthandoff: 02/24/2017

---
# <a name="run-time-object-model-services"></a>ランタイム オブジェクト モデル サービス
クラスは、 [CObject](../../mfc/reference/cobject-class.md)と[CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)ランタイム クラス情報、シリアル化、およびオブジェクトの動的生成へのアクセスなど、いくつかのオブジェクトのサービスをカプセル化します。 すべてのクラスから派生した`CObject`この機能を継承します。  
  
 ランタイム クラス情報へのアクセスには、実行時に、オブジェクトのクラスに関する情報を確認することができます。 余分な型チェック関数の引数を使用して、オブジェクトのクラスに基づく特殊なコードを記述する必要があります必要がある場合は、実行時にオブジェクトのクラスを判断することをお勧めします。 ランタイム クラス情報は、C++ 言語によって直接サポートされていません。  
  
 シリアル化は、ファイルからの書き込みまたはオブジェクトの内容を読み取り中のプロセスです。 シリアル化を使用すると、アプリケーションの終了後も、オブジェクトの内容を保存します。 アプリケーションが再起動したときに、オブジェクトはその後ファイルから読み取ることができます。 このようなデータ オブジェクトは「固定」と呼ばれます  
  
 動的オブジェクトの作成では、実行時に指定したクラスのオブジェクトを作成することができます。 たとえば、ドキュメント、ビュー、およびフレーム オブジェクト必要がありますサポートを動的に作成フレームワークは、それらを動的に作成する必要があるためです。  
  
 次の表は、ランタイム クラス情報、シリアル化、および動的な作成をサポートする MFC のマクロを一覧表示します。  
  
 これらの実行時のオブジェクトのサービスとシリアル化の詳細については、記事を参照してください。 [CObject クラス: クラス情報にアクセスする](../../mfc/accessing-run-time-class-information.md)です。  
  
### <a name="run-time-object-model-services-macros"></a>ランタイム オブジェクト モデル サービス マクロ  
  
|||  
|-|-|  
|[DECLARE_DYNAMIC](#declare_dynamic)|(クラス宣言で使用する必要があります) のランタイム クラス情報にアクセスできます。|  
|[DECLARE_DYNCREATE](#declare_dyncreate)|動的に作成し、(クラス宣言で使用する必要があります) のランタイム クラス情報へのアクセスを使用できます。|  
|[DECLARE_SERIAL](#declare_serial)|シリアル化と (クラス宣言で使用する必要があります) のランタイム クラス情報へのアクセスを使用できます。|  
|[新規クラス](#implement_dynamic)|(クラスの実装で使用する必要があります) のランタイム クラス情報にアクセスできます。|  
|[IMPLEMENT_DYNCREATE](#implement_dyncreate)|動的な作成および実行時の情報 (クラスの実装で使用する必要があります) へのアクセスを使用できます。|  
|[IMPLEMENT_SERIAL](#implement_serial)|シリアル化と (クラスの実装で使用する必要があります) のランタイム クラス情報へのアクセスを許可します。|  
|[対象となります。](#runtime_class)|返します。、`CRuntimeClass`名前付きのクラスに対応する構造体。|  


 通常、OLE には、実行時にオブジェクトの動的生成が必要です。 たとえば、OLE サーバー アプリケーションは、クライアントからの要求に応答 OLE アイテムを動的に作成できる必要があります。 同様に、オートメーション サーバーは、オートメーション クライアントからの要求に応答で項目を作成できる必要があります。  
  
 Microsoft Foundation Class ライブラリは、OLE に特定の&2; つのマクロを提供します。  
  
### <a name="dynamic-creation-of-ole-objects"></a>OLE オブジェクトの動的生成  
  
|||  
|-|-|  
|[DECLARE_OLECREATE](#declare_olecreate)|OLE オートメーションを通じて作成されるオブジェクトを有効にします。|  
|[IMPLEMENT_OLECREATE](#implement_olecreate)|OLE システムによって作成されるオブジェクトを有効にします。|  
  
##  <a name="a-namedeclaredynamica--declaredynamic"></a><a name="declare_dynamic"></a>DECLARE_DYNAMIC  
 クラスを派生している場合、オブジェクトのクラスに関する実行時の情報にアクセスする機能が追加されて`CObject`します。  
  
```
DECLARE_DYNAMIC(class_name) 
```  
  
### <a name="parameters"></a>パラメーター  
 *それ以外*  
 クラスの実際の名前。  
  
### <a name="remarks"></a>コメント  
 追加、`DECLARE_DYNAMIC`クラスのヘッダー (.h) モジュールにマクロがこのクラスのオブジェクトへのアクセスが必要なすべての .cpp モジュール内、そのモジュールを含めます。  
  
 使用する場合、 **DECLARE**_**動的**と`IMPLEMENT_DYNAMIC`マクロの説明に従って、使用して、`RUNTIME_CLASS`マクロと`CObject::IsKindOf`関数を実行時に、オブジェクトのクラスを決定します。  
  
 場合`DECLARE_DYNAMIC`し、クラス宣言に含まれる`IMPLEMENT_DYNAMIC`クラスの実装に含める必要があります。  
  
 詳細については、`DECLARE_DYNAMIC`マクロを参照してください[CObject クラス トピック](../../mfc/using-cobject.md)します。  
  
### <a name="example"></a>例  
 例を参照してください[IMPLEMENT_DYNAMIC](#implement_dynamic)します。  

### <a name="requirements"></a>要件  
 **ヘッダー:** afx.h 

##  <a name="a-namedeclaredyncreatea--declaredyncreate"></a><a name="declare_dyncreate"></a>DECLARE_DYNCREATE  
 により、オブジェクトの`CObject`-実行時に動的に作成するクラスを派生します。  
  
```
DECLARE_DYNCREATE(class_name)   
```  
  
### <a name="parameters"></a>パラメーター  
 *それ以外*  
 クラスの実際の名前。  
  
### <a name="remarks"></a>コメント  
 フレームワークでは、この機能を使用して、新しいオブジェクトを動的に作成します。 たとえば、新しいビュー、新しいドキュメントを開くときに作成します。 ドキュメント、ビュー、およびフレーム クラスは、フレームワークは、それらを動的に作成する必要があるため動的な作成をサポートする必要があります。  
  
 追加、`DECLARE_DYNCREATE`クラスには、.h モジュール内のマクロは、このクラスのオブジェクトへのアクセスが必要なすべての .cpp モジュールにそのモジュールを追加する、です。  
  
 場合`DECLARE_DYNCREATE`し、クラス宣言に含まれる`IMPLEMENT_DYNCREATE`クラスの実装に含める必要があります。  
  
 詳細については、`DECLARE_DYNCREATE`マクロを参照してください[CObject クラス トピック](../../mfc/using-cobject.md)します。  
  
> [!NOTE]
>  `DECLARE_DYNCREATE`マクロには、すべての機能が含まれている`DECLARE_DYNAMIC`します。  
  
### <a name="example"></a>例  
 例を参照してください[IMPLEMENT_DYNCREATE](#implement_dyncreate)します。  

### <a name="requirements"></a>要件  
 **ヘッダー:** afx.h 

##  <a name="a-namedeclareseriala--declareserial"></a><a name="declare_serial"></a>DECLARE_SERIAL  
 必要な C++ ヘッダーのコードを生成、`CObject`の派生クラスで、シリアル化することができます。  
  
```
DECLARE_SERIAL(class_name)   
```  
  
### <a name="parameters"></a>パラメーター  
 *それ以外*  
 クラスの実際の名前。  
  
### <a name="remarks"></a>コメント  
 シリアル化は、書き込み、またはオブジェクトの内容を読み取るファイルからのプロセスです。  
  
 使用して、`DECLARE_SERIAL`モジュールでは、.h、マクロし、このクラスのオブジェクトへのアクセスが必要なすべての .cpp モジュールでそのモジュールを含めます。  
  
 場合`DECLARE_SERIAL`し、クラス宣言に含まれる`IMPLEMENT_SERIAL`クラスの実装に含める必要があります。  
  
 `DECLARE_SERIAL`マクロには、すべての機能が含まれている`DECLARE_DYNAMIC`と`DECLARE_DYNCREATE`です。  
  
 使用することができます、 **AFX_API**を自動的にエクスポートするマクロ、`CArchive`抽出演算子のクラスを使用する、`DECLARE_SERIAL`と`IMPLEMENT_SERIAL`マクロです。 次のコードをクラス宣言 (.h ファイルにあります) を囲みます。  
  
 [!code-cpp[NVC_MFCCObjectSample&#20;](../../mfc/codesnippet/cpp/run-time-object-model-services_1.h)]  
  
 詳細については、`DECLARE_SERIAL`マクロを参照してください[CObject クラス トピック](../../mfc/using-cobject.md)します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCObjectSample #&21;](../../mfc/codesnippet/cpp/run-time-object-model-services_2.h)]  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** afx.h 

##  <a name="a-nameimplementdynamica--implementdynamic"></a><a name="implement_dynamic"></a>新規クラス  
 動的なのために必要な C++ コードを生成`CObject`-クラス名と、階層内の位置に、実行時アクセス権を持つクラスを派生します。  
  
```
IMPLEMENT_DYNAMIC(class_name, base_class_name)  
```  
  
### <a name="parameters"></a>パラメーター  
 *それ以外*  
 クラスの実際の名前。  
  
 `base_class_name`  
 基本クラスの名前。  
  
### <a name="remarks"></a>コメント  
 使用して、`IMPLEMENT_DYNAMIC`マクロで、.cpp モジュール、およびリンク結果のオブジェクト コードの&1; 回だけです。  
  
 詳細については、次を参照してください。 [CObject クラス トピック](../../mfc/using-cobject.md)します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCObjectSample&#2;](../../mfc/codesnippet/cpp/run-time-object-model-services_3.h)]  
  
 [!code-cpp[NVC_MFCCObjectSample&#3;](../../mfc/codesnippet/cpp/run-time-object-model-services_4.cpp)]  

### <a name="requirements"></a>要件  
 **ヘッダー:** afx.h 

##  <a name="a-nameimplementdyncreatea--implementdyncreate"></a><a name="implement_dyncreate"></a>IMPLEMENT_DYNCREATE  
 により、オブジェクトの`CObject`-実行時に動的に作成するクラスの派生で使用すると、`DECLARE_DYNCREATE`マクロです。  
  
```
IMPLEMENT_DYNCREATE(class_name, base_class_name)   
```  
  
### <a name="parameters"></a>パラメーター  
 *それ以外*  
 クラスの実際の名前。  
  
 `base_class_name`  
 基本クラスの実際の名前。  
  
### <a name="remarks"></a>コメント  
 フレームワークでは、この機能を使用して、新しいオブジェクトを動的に作成、たとえば、シリアル化中にディスクからオブジェクトを読み取る際にします。 追加、`IMPLEMENT_DYNCREATE`クラス実装ファイルでマクロです。 詳細については、次を参照してください。 [CObject クラス トピック](../../mfc/using-cobject.md)します。  
  
 使用する場合、`DECLARE_DYNCREATE`と`IMPLEMENT_DYNCREATE`マクロを使用して、`RUNTIME_CLASS`マクロと`CObject::IsKindOf`メンバー関数を実行時に、オブジェクトのクラスを決定します。  
  
 場合`DECLARE_DYNCREATE`し、クラス宣言に含まれる`IMPLEMENT_DYNCREATE`クラスの実装に含める必要があります。  
  
 このマクロ定義で、クラスの既定のコンス トラクターを呼び出すことに注意してください。 重要なコンス トラクターが明示的にクラスが実装されている場合にも明示的にも既定のコンス トラクターを実装する必要があります。 既定のコンス トラクターは、クラスに追加できます**プライベート**または**保護されている**メンバーのセクションでは、クラスの実装の外部から呼び出されるを防ぐことにします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCObjectSample #&22;](../../mfc/codesnippet/cpp/run-time-object-model-services_5.h)]  
  
 [!code-cpp[NVC_MFCCObjectSample 第&23;](../../mfc/codesnippet/cpp/run-time-object-model-services_6.cpp)]  

### <a name="requirements"></a>要件  
 **ヘッダー:** afx.h 

##  <a name="a-nameimplementseriala--implementserial"></a><a name="implement_serial"></a>IMPLEMENT_SERIAL  
 動的なのために必要な C++ コードを生成`CObject`-クラス名と、階層内の位置に、実行時アクセス権を持つクラスを派生します。  
  
```
IMPLEMENT_SERIAL(class_name, base_class_name, wSchema)  
```  
  
### <a name="parameters"></a>パラメーター  
 *それ以外*  
 クラスの実際の名前。  
  
 `base_class_name`  
 基本クラスの名前。  
  
 *wSchema*  
 A **UINT**したアーカイブの逆シリアル化をプログラムを特定し、作成したデータを処理できるようにエンコードされる「バージョン番号」は前のバージョンをプログラムします。 クラスのスキーマの番号が â € することはできません"は&1;。  
  
### <a name="remarks"></a>コメント  
 使用して、`IMPLEMENT_SERIAL`マクロ .cpp モジュールで&1; 回だけ作成されるオブジェクト コードをリンクします。  
  
 使用することができます、 **AFX_API**を自動的にエクスポートするマクロ、`CArchive`抽出演算子のクラスを使用する、`DECLARE_SERIAL`と`IMPLEMENT_SERIAL`マクロです。 次のコードをクラス宣言 (.h ファイルにあります) を囲みます。  
  
 [!code-cpp[NVC_MFCCObjectSample&#20;](../../mfc/codesnippet/cpp/run-time-object-model-services_1.h)]  
  
 詳細については、次を参照してください。、 [CObject クラス トピック](../../mfc/using-cobject.md)します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCObjectSample #&24;](../../mfc/codesnippet/cpp/run-time-object-model-services_7.cpp)]  

### <a name="requirements"></a>要件  
 **ヘッダー:** afx.h 

##  <a name="a-nameruntimeclassa--runtimeclass"></a><a name="runtime_class"></a>対象となります。  
 C++ クラスの名前から、実行時のクラス構造体を取得します。  
  
```
RUNTIME_CLASS(class_name)  
```  
  
### <a name="parameters"></a>パラメーター  
 *それ以外*  
 (引用符で囲まれていない) クラスの実際の名前。  
  
### <a name="remarks"></a>コメント  
 `RUNTIME_CLASS`ポインターを返す、 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)で指定されたクラスの構造体*、それ以外*します。 のみ`CObject`の派生クラスで宣言された`DECLARE_DYNAMIC`、 `DECLARE_DYNCREATE`、または`DECLARE_SERIAL`へのポインターを返す、`CRuntimeClass`構造体。  
  
 詳細については、次を参照してください。 [CObject クラス トピック](../../mfc/using-cobject.md)します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCObjectSample&#25;](../../mfc/codesnippet/cpp/run-time-object-model-services_8.cpp)]  

### <a name="requirements"></a>要件  
 **ヘッダー:** afx.h 
   
##  <a name="a-namedeclareolecreatea--declareolecreate"></a><a name="declare_olecreate"></a>DECLARE_OLECREATE  
 により、オブジェクトの`CCmdTarget`-OLE オートメーションを通じて作成されるクラスを派生します。  
  
```
DECLARE_OLECREATE(class_name) 
```  
  
### <a name="parameters"></a>パラメーター  
 *それ以外*  
 クラスの実際の名前。  
  
### <a name="remarks"></a>コメント  
 このマクロは、この型のオブジェクトを作成するその他の OLE 対応のアプリケーションを使用できます。  
  
 追加、`DECLARE_OLECREATE`クラスには、.h モジュール内のマクロし、このクラスのオブジェクトへのアクセスが必要なすべての .cpp モジュールでそのモジュールを含めます。  
  
 場合`DECLARE_OLECREATE`し、クラス宣言に含まれる`IMPLEMENT_OLECREATE`クラスの実装に含める必要があります。 クラスの宣言を使用して、`DECLARE_OLECREATE`もを使用する必要があります`DECLARE_DYNCREATE`または`DECLARE_SERIAL`です。  

### <a name="requirements"></a>要件  
 **ヘッダー**: afxdisp.h  

##  <a name="a-nameimplementolecreatea--implementolecreate"></a><a name="implement_olecreate"></a>IMPLEMENT_OLECREATE  
 このいずれかのマクロまたは[IMPLEMENT_OLECREATE_FLAGS](http://msdn.microsoft.com/library/d1589f6a-5a69-4742-b07c-4c621cfd040d)を使用するクラスの実装ファイルに表示する必要があります`DECLARE_OLECREATE`します。  
  
```
IMPLEMENT_OLECREATE(class_name, external_name, l, w1, w2, b1, b2, b3, b4, b5, b6, b7, b8)  
```  
  
### <a name="parameters"></a>パラメーター  
 *それ以外*  
 クラスの実際の名前。  
  
 *external_name*  
 (引用符で囲まれた) 他のアプリケーションに公開されているオブジェクト名。  
  
 *l*, *w1*, *w2*, *b1*, *b2*, *b3*, *b4*, *b5*, *b6*, *b7*, *b8*  
 クラスのコンポーネント**CLSID**します。  
  
### <a name="remarks"></a>コメント  
  
> [!NOTE]
>  使用する場合`IMPLEMENT_OLECREATE`既定では、1 つのスレッド モデルのみをサポートします。 使用する場合`IMPLEMENT_OLECREATE_FLAGS`、オブジェクトのサポートを使用しているスレッド モデルを指定する、`nFlags`パラメーター。  
  
 外部の名前は、その他のアプリケーションに公開される識別子です。 クライアント アプリケーションでは、外部の名前を使用して、オートメーション サーバーからこのクラスのオブジェクトを要求します。  
  
 OLE クラス ID は、オブジェクトの一意な 128 ビット識別子です。 構成は次のいずれかの**長い**、2 つ**WORD**秒、および&8;**バイト**で表される、s *l*、 *w1*、 *w2*、および*b1*を通じて*b8*構文の説明にします。 アプリケーション ウィザードとコードのウィザードでは、必要に応じての一意の OLE クラス Id を作成します。  

### <a name="requirements"></a>要件  
 **ヘッダー**: afxdisp.h 

## <a name="see-also"></a>関連項目  
 [マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)

