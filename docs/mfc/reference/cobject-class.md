---
title: "CObject クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CObject
- AFX/CObject
- AFX/CObject::CObject
- AFX/CObject::AssertValid
- AFX/CObject::Dump
- AFX/CObject::GetRuntimeClass
- AFX/CObject::IsKindOf
- AFX/CObject::IsSerializable
- AFX/CObject::Serialize
dev_langs:
- C++
helpviewer_keywords:
- base classes, MFC objects
- objects [C++], base class for MFC
- object classes
- CObject class
ms.assetid: 95e9acd3-d9eb-4ac0-b52b-ca4a501a7a3a
caps.latest.revision: 22
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: d411b9da8618eaac57045a1db05251517422976a
ms.lasthandoff: 02/24/2017

---
# <a name="cobject-class"></a>CObject クラス
MFC ライブラリの重要な基底クラスです。  
  
## <a name="syntax"></a>構文  
  
```  
class AFX_NOVTABLE CObject  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="protected-constructors"></a>プロテクト コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CObject::CObject](#cobject)|既定のコンストラクター|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[Cobject::assertvalid](#assertvalid)|このオブジェクトの整合性を検証します。|  
|[CObject::Dump](#dump)|このオブジェクトの診断用のダンプを生成します。|  
|[CObject::GetRuntimeClass](#getruntimeclass)|返します。、`CRuntimeClass`このオブジェクトのクラスに対応する構造体。|  
|[使うため](#iskindof)|所定のクラスにこのオブジェクトの関係をテストします。|  
|[CObject::IsSerializable](#isserializable)|このオブジェクトをシリアル化できるかどうかを確認するテストです。|  
|[指定](#serialize)|読み込みまたはアーカイブから/にオブジェクトを格納します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CObject::operator の削除](#operator_delete)|特殊な**削除**演算子。|  
|[新しい CObject::operator](#operator_new)|特殊な**新しい**演算子。|  
  
## <a name="remarks"></a>コメント  
 などのライブラリのクラスだけでなくルートとして機能し`CFile`と`CObList`、記述するクラスに対してもします。 `CObject`などの基本的なサービスを提供します  
  
-   シリアル化のサポート  
  
-   ランタイム クラス情報  
  
-   オブジェクトの診断出力  
  
-   コレクション クラスとの互換性  
  
 なお`CObject`多重継承をサポートしていません。 派生クラスが&1; つのみに存在`CObject`、基本クラスなどを`CObject`階層の一番左にある必要があります。 許される、ただし、構造を持っていると非-`CObject`の右側の多重継承の分岐内のクラスを派生します。  
  
 主なメリットを実感`CObject`派生クラスの実装との宣言の省略可能なマクロの一部を使用する場合。  
  
 第&1; レベル マクロ[DECLARE_DYNAMIC](run-time-object-model-services.md#declare_dynamic)と[IMPLEMENT_DYNAMIC](run-time-object-model-services.md#implement_dynamic)実行時に、クラス名と、階層内での位置にアクセスを許可します。 さらに、これにより、意味のある診断をダンプします。  
  
 第&2; レベル マクロ[DECLARE_SERIAL](run-time-object-model-services.md#declare_serial)と[IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial)第&1; レベルのマクロのすべての機能を含む、およびそれらを使用するシリアル化する""と「アーカイブします」のオブジェクト。  
  
 一般に Microsoft Foundation class と C++ のクラスを派生させることと、使用方法についての`CObject`を参照してください[を使用して CObject](../../mfc/using-cobject.md)と[シリアル化](../../mfc/serialization-in-mfc.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `CObject`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afx.h  
  
##  <a name="assertvalid"></a>Cobject::assertvalid  
 このオブジェクトの整合性を検証します。  
  
```  
virtual void AssertValid() const;  
```  
  
### <a name="remarks"></a>コメント  
 `AssertValid`内部の状態をチェックしてこのオブジェクトの有効性チェックを実行します。 ライブラリのデバッグ バージョンで`AssertValid`をアサートし、アサーションが失敗した行番号とファイル名を一覧表示するメッセージでプログラムを終了したがって可能性があります。  
  
 独自のクラスを記述するとき、`AssertValid`自分とクラスの他のユーザー用の診断サービスを提供する関数。 オーバーライドされた`AssertValid`通常を呼び出す、`AssertValid`派生クラス独自のデータ メンバーをチェックする前に、基底クラスの関数です。  
  
 `AssertValid`は、 **const**関数は、テスト中に、オブジェクトの状態を変更する許可されていません。 派生クラス`AssertValid`関数は例外をスローする必要がありますが、無効なオブジェクトのデータを検出するかどうかではなくをアサートします。  
  
 "Validity"の定義は、オブジェクトのクラスに依存します。 原則として、関数が、「簡易チェック」を実行します。 つまり、オブジェクトに他のオブジェクトへのポインターが含まれている場合を確認するかどうか、ポインターが null でないが、有効性がポインターで参照されるオブジェクトでのテストを実行する必要があります。  
  
### <a name="example"></a>例  
 参照してください[使われて](../../mfc/reference/coblist-class.md#coblist)の一覧については、`CAge`すべてで使用されるクラス`CObject`例です。  
  
 [!code-cpp[NVC_MFCCObjectSample&#7;](../../mfc/codesnippet/cpp/cobject-class_1.cpp)]  
  
 別の例では、次を参照してください。 [AfxDoForAllObjects](diagnostic-services.md#afxdoforallobjects)します。  
  
##  <a name="cobject"></a>CObject::CObject  
 これらの関数は、標準`CObject`のコンス トラクターです。  
  
```  
CObject();  
CObject(const CObject& objectSrc);
```  
  
### <a name="parameters"></a>パラメーター  
 *objectSrc*  
 別の参照`CObject`  
  
### <a name="remarks"></a>コメント  
 既定のバージョンは、派生クラスのコンス トラクターによって自動的に呼び出されます。  
  
 クラスがシリアル化可能な場合 (が組み込まれている、`IMPLEMENT_SERIAL`マクロ)、クラス宣言での既定のコンス トラクター (引数なしコンス トラクター) があります。 既定のコンス トラクターを必要がない場合、private を宣言または"empty"のコンス トラクターを保護します。 詳細については、次を参照してください。[を使用して CObject](../../mfc/using-cobject.md)します。  
  
 標準的な C++ 既定クラスのコピー コンス トラクターは、メンバーごとのコピー。 秘密のプレゼンス`CObject`クラスのコピー コンス トラクターが必要なは利用できない場合、コピー コンス トラクターは、コンパイラ エラー メッセージを保証します。 クラスには、この機能が必要な場合にしたがって、コピー コンストラクタを提供する必要があります。  
  
### <a name="example"></a>例  
 参照してください[使われて](../../mfc/reference/coblist-class.md#coblist)の一覧については、`CAge`で使用されるクラス、`CObject`例です。  
  
 [!code-cpp[NVC_MFCCObjectSample&#8;](../../mfc/codesnippet/cpp/cobject-class_2.cpp)]  
  
##  <a name="dump"></a>CObject::Dump  
 オブジェクトの内容をダンプする[CDumpContext](../../mfc/reference/cdumpcontext-class.md)オブジェクトです。  
  
```  
virtual void Dump(CDumpContext& dc) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `dc`  
 通常、ダンプの診断ダンプ コンテキスト`afxDump`します。  
  
### <a name="remarks"></a>コメント  
 独自のクラスを記述するとき、`Dump`自分とクラスの他のユーザー用の診断サービスを提供する関数。 オーバーライドされた`Dump`通常を呼び出す、`Dump`派生クラス独自のデータ メンバーを印刷する前に、基底クラスの関数です。 `CObject::Dump`クラスで使用する場合に、クラスの名前を表示する、`IMPLEMENT_DYNAMIC`または`IMPLEMENT_SERIAL`マクロです。  
  
> [!NOTE]
>  `Dump`関数がその出力の末尾の改行文字に出力することはありません。  
  
 `Dump`呼び出しでは、Microsoft Foundation Class ライブラリのデバッグ バージョンでのみ意味をなします。 呼び出し、関数宣言と関数の実装を囲む必要があります**#ifdef _DEBUG** /  `#endif`に対して条件付きコンパイル ステートメントです。  
  
 `Dump`は、 **const**関数は、ダンプ中に、オブジェクトの状態を変更する許可されていません。  
  
 [CDumpContext カーソル (<)> </)> ](../../mfc/reference/cdumpcontext-class.md#operator_lt_lt)呼び出し`Dump`ときに、`CObject`ポインターを挿入します。  
  
 `Dump`オブジェクトのダンプを「非循環」のみを許可します。 たとえば、オブジェクトの一覧をダンプすることができますが、スタックがオーバーフローする一方のオブジェクトがリスト自体の場合は、最終的には。  
  
### <a name="example"></a>例  
 参照してください[使われて](../../mfc/reference/coblist-class.md#coblist)の一覧については、`CAge`すべてで使用されるクラス`CObject`例です。  
  
 [!code-cpp[NVC_MFCCObjectSample&#9;](../../mfc/codesnippet/cpp/cobject-class_3.cpp)]  
  
##  <a name="getruntimeclass"></a>CObject::GetRuntimeClass  
 返します。、`CRuntimeClass`このオブジェクトのクラスに対応する構造体。  
  
```  
virtual CRuntimeClass* GetRuntimeClass() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ポインター、 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)構造体がこのオブジェクトのクラスに対応することはありません**NULL**します。  
  
### <a name="remarks"></a>コメント  
 1 つである`CRuntimeClass`構造`CObject`-クラスを派生します。 構造体のメンバーは次のとおりです。  
  
- **LPCSTR m_lpszClassName** ASCII クラス名を含む null で終わる文字列。  
  
- **int m_nObjectSize** (バイト単位) のオブジェクトのサイズ。 オブジェクトは、割り当てられたメモリを指すデータ メンバーを持っている場合はそのメモリのサイズは含まれません。  
  
- **UINT m_wSchema**スキーマ番号 (– 1 をシリアル化されないクラス)。 参照してください、 [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial)スキーマ番号の詳細についてはマクロです。  
  
- **CObject\* (PASCAL\* m_pfnCreateObject) ()**クラスのオブジェクトを作成する既定のコンス トラクターへの関数ポインター (有効なクラスは、動的作成をサポートしている場合にのみを返します**NULL**)。  
  
- **CRuntimeClass\* (PASCAL\* m_pfn_GetBaseClass) ()**場合 AFXDLL バージョンの MFC アプリケーションを動的にリンクすると、関数へのポインターを返す、`CRuntimeClass`基本クラスの構造体。  
  
- **CRuntimeClass\* m_pBaseClass** 、アプリケーションが MFC へのポインターを静的にリンクされているかどうか、`CRuntimeClass`基本クラスの構造体。  
  
 この関数の使用を必要と、 [IMPLEMENT_DYNAMIC](run-time-object-model-services.md#implement_dynamic)、 [IMPLEMENT_DYNCREATE](run-time-object-model-services.md#implement_dyncreate)、または[IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial)マクロで、クラスの実装です。 それ以外の場合正しくない結果が表示されます。  
  
### <a name="example"></a>例  
 参照してください[使われて](../../mfc/reference/coblist-class.md#coblist)の一覧については、`CAge`すべてで使用されるクラス`CObject`例です。  
  
 [!code-cpp[NVC_MFCCObjectSample&#10;](../../mfc/codesnippet/cpp/cobject-class_4.cpp)]  
  
##  <a name="iskindof"></a>使うため  
 所定のクラスにこのオブジェクトの関係をテストします。  
  
```  
BOOL IsKindOf(const CRuntimeClass* pClass) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `pClass`  
 ポインター、 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)構造に関連付けられている、 `CObject`-クラスを派生します。  
  
### <a name="return-value"></a>戻り値  
 オブジェクトは、クラスに対応している場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 この関数をテスト`pClass`するかどうか、指定したクラスのオブジェクトは、(1)、または (2) は、指定したクラスから派生したクラスのオブジェクトを参照してください。 この関数の動作で宣言されたクラスに対してのみ、 [DECLARE_DYNAMIC](run-time-object-model-services.md#declare_dynamic)、 [DECLARE_DYNCREATE](run-time-object-model-services.md#declare_dyncreate)、または[DECLARE_SERIAL](run-time-object-model-services.md#declare_serial)マクロです。  
  
 C++ のポリモーフィズム機能できないためには、広範囲にこの関数を使用しないでください。 代わりに、仮想関数を使用します。  
  
### <a name="example"></a>例  
 参照してください[使われて](../../mfc/reference/coblist-class.md#coblist)の一覧については、`CAge`すべてで使用されるクラス`CObject`例です。  
  
 [!code-cpp[NVC_MFCCObjectSample&#11;](../../mfc/codesnippet/cpp/cobject-class_5.cpp)]  
  
##  <a name="isserializable"></a>CObject::IsSerializable  
 このオブジェクトはシリアル化に適しているかどうかをテストします。  
  
```  
BOOL IsSerializable() const;  
```  
  
### <a name="return-value"></a>戻り値  
 この場合は 0 以外のオブジェクトをシリアル化することができます。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 シリアル化できるクラス、その宣言が含まれていなければなりません、 [DECLARE_SERIAL](run-time-object-model-services.md#declare_serial)マクロ、および実装を含める必要があります、 [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial)マクロです。  
  
> [!NOTE]
>  この関数は無効です。  
  
### <a name="example"></a>例  
 参照してください[使われて](../../mfc/reference/coblist-class.md#coblist)の一覧については、`CAge`すべてで使用されるクラス`CObject`例です。  
  
 [!code-cpp[NVC_MFCCObjectSample&#12;](../../mfc/codesnippet/cpp/cobject-class_6.cpp)]  
  
##  <a name="operator_delete"></a>CObject::operator の削除  
 ライブラリのリリース版に関する演算子**削除**演算子によって割り当てられたメモリを解放**新しい**します。  
  
```  
void PASCAL operator delete(void* p);

 
void PASCAL operator delete(
    void* p,
    void* pPlace);

 
void PASCAL operator delete(
    void* p,  
    LPCSTR lpszFileName,  
    int nLine);
```  
  
### <a name="remarks"></a>コメント  
 デバッグ バージョンに演算子**削除**メモリ リークを検出するために設計された割り当て監視のスキームに参加しています。  
  
 コード行を使用する場合  
  
 [!code-cpp[NVC_MFCCObjectSample&#14;](../../mfc/codesnippet/cpp/cobject-class_7.cpp)]  
  
 任意のコード行の前に、します。CPP ファイルを&3; 番目のバージョン**削除**使用は後でレポートの割り当てられたブロックでファイル名と行番号を格納します。 余分なパラメーターを指定することについて心配する必要はありません。マクロでその処理されるためです。  
  
 使用しない場合でも`DEBUG_NEW`リーク検出の取得もデバッグ モードで前に説明したソース ファイルの行番号のレポート作成しなくてもします。  
  
 演算子をオーバーライドする場合は**新しい**と**削除**、この診断機能が多少低下します。  
  
### <a name="example"></a>例  
 参照してください[使われて](../../mfc/reference/coblist-class.md#coblist)の一覧については、`CAge`で使用されるクラス、`CObject`例です。  
  
 [!code-cpp[NVC_MFCCObjectSample&#15;](../../mfc/codesnippet/cpp/cobject-class_8.cpp)]  
  
##  <a name="operator_new"></a>新しい CObject::operator  
 ライブラリのリリース版に関する演算子**新しい**と同様の方法で最適なメモリ割り当てを実行`malloc`します。  
  
```  
void* PASCAL operator new(size_t nSize);  
void* PASCAL operator new(size_t, void* p);

 
void* PASCAL operator new(
    size_t nSize,  
    LPCSTR lpszFileName,  
    int nLine);
```  
  
### <a name="remarks"></a>コメント  
 デバッグ バージョンに演算子**新しい**メモリ リークを検出するために設計された割り当て監視のスキームに参加しています。  
  
 コード行を使用する場合  
  
 [!code-cpp[NVC_MFCCObjectSample&#14;](../../mfc/codesnippet/cpp/cobject-class_7.cpp)]  
  
 任意のコード行の前に、します。CPP ファイルの&2; 番目のバージョン**新しい**使用は後でレポートの割り当てられたブロックでファイル名と行番号を格納します。 余分なパラメーターを指定することについて心配する必要はありません。マクロでその処理されるためです。  
  
 使用しない場合でも`DEBUG_NEW`リーク検出の取得もデバッグ モードで前に説明したソース ファイルの行番号のレポート作成しなくてもします。  
  
> [!NOTE]
>  この演算子をオーバーライドすると、する必要がありますもまた上書き**削除**します。 標準ライブラリを使用しないで**_new_handler**関数です。  
  
### <a name="example"></a>例  
 参照してください[使われて](../../mfc/reference/coblist-class.md#coblist)の一覧については、`CAge`で使用されるクラス、`CObject`例です。  
  
 [!code-cpp[NVC_MFCCObjectSample&#16;](../../mfc/codesnippet/cpp/cobject-class_9.h)]  
  
##  <a name="serialize"></a>指定  
 アーカイブに対して、このオブジェクトの読み取りまたは書き込みを行います。  
  
```  
virtual void Serialize(CArchive& ar);
```  
  
### <a name="parameters"></a>パラメーター  
 `ar`  
 A`CArchive`をシリアル化するオブジェクト。  
  
### <a name="remarks"></a>コメント  
 オーバーライドする必要があります`Serialize`シリアル化する各クラスに対してです。 オーバーライドされた`Serialize`、まず、`Serialize`基底クラスの関数です。  
  
 使用する必要もあります、 [DECLARE_SERIAL](run-time-object-model-services.md#declare_serial)して、クラス宣言内のマクロを使用する必要があります、 [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial)マクロの実装です。  
  
 使用[とき](../../mfc/reference/carchive-class.md#isloading)または[用](../../mfc/reference/carchive-class.md#isstoring)アーカイブの読み込みまたは保存するかどうかを決定します。  
  
 `Serialize`によって呼び出される[CArchive::ReadObject](../../mfc/reference/carchive-class.md#readobject)と[CArchive::WriteObject](../../mfc/reference/carchive-class.md#writeobject)します。 これらの関数が関連付けられている、`CArchive`挿入演算子 ( ** < \< **) と抽出演算子 ( ** >> **)。  
  
 シリアル化の例については、記事を参照して[シリアル化: オブジェクトのシリアル化](../../mfc/serialization-serializing-an-object.md)します。  
  
### <a name="example"></a>例  
 参照してください[使われて](../../mfc/reference/coblist-class.md#coblist)の一覧については、`CAge`すべてで使用されるクラス`CObject`例です。  
  
 [!code-cpp[NVC_MFCCObjectSample&#13;](../../mfc/codesnippet/cpp/cobject-class_10.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)




