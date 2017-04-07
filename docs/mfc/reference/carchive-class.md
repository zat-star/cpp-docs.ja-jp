---
title: "CArchive クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CArchive
- AFX/CArchive
- AFX/CArchive::CArchive
- AFX/CArchive::Abort
- AFX/CArchive::Close
- AFX/CArchive::Flush
- AFX/CArchive::GetFile
- AFX/CArchive::GetObjectSchema
- AFX/CArchive::IsBufferEmpty
- AFX/CArchive::IsLoading
- AFX/CArchive::IsStoring
- AFX/CArchive::MapObject
- AFX/CArchive::Read
- AFX/CArchive::ReadClass
- AFX/CArchive::ReadObject
- AFX/CArchive::ReadString
- AFX/CArchive::SerializeClass
- AFX/CArchive::SetLoadParams
- AFX/CArchive::SetObjectSchema
- AFX/CArchive::SetStoreParams
- AFX/CArchive::Write
- AFX/CArchive::WriteClass
- AFX/CArchive::WriteObject
- AFX/CArchive::WriteString
- AFX/CArchive::m_pDocument
dev_langs:
- C++
helpviewer_keywords:
- I/O [MFC], archiving objects
- CArchive class
- serialization [C++], CArchive class
- storage [C++], CArchive class
- data storage [C++], CArchive class
ms.assetid: 9e950d23-b874-456e-ae4b-fe00781a7699
caps.latest.revision: 21
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
ms.openlocfilehash: 501b365678a45148aabe638ff341f3ae995e4ab5
ms.lasthandoff: 02/24/2017

---
# <a name="carchive-class"></a>CArchive クラス
オブジェクトを削除した後も保持する永続的なバイナリ形式 (通常はディスク ストレージ) にオブジェクトの複雑なネットワークを保存できます。  
  
## <a name="syntax"></a>構文  
  
```  
class CArchive  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CArchive::CArchive](#carchive)|
          `CArchive` オブジェクトを作成します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CArchive::Abort](#abort)|例外をスローせず、アーカイブを閉じます。|  
|[CArchive::Close](#close)|書き込まれていないデータをフラッシュし、切断、`CFile`です。|  
|[ときは](#flush)|アーカイブ バッファーから書き込まれていないデータをフラッシュします。|  
|[CArchive::GetFile](#getfile)|取得、`CFile`このアーカイブ対象のオブジェクトのポインター。|  
|[CArchive::GetObjectSchema](#getobjectschema)|呼び出される、`Serialize`関数は、逆シリアル化されるオブジェクトのバージョンを決定します。|  
|[CArchive::IsBufferEmpty](#isbufferempty)|Windows ソケットの中にバッファーが空になっているかどうかを決定プロセスを受信します。|  
|[場合](#isloading)|アーカイブを読み込むかどうかを決定します。|  
|[用](#isstoring)|アーカイブを格納するかどうかを決定します。|  
|[CArchive::MapObject](#mapobject)|ファイルにシリアル化されませんが、参照のサブオブジェクトとして提供されるマップ内のオブジェクトを配置します。|  
|[読み書きするとき](#read)|実際のバイト数を読み取ります。|  
|[場合](#readclass)|クラスの参照が格納されていた読み取り`WriteClass`します。|  
|[CArchive::ReadObject](#readobject)|オブジェクトの`Serialize`の読み込みの関数です。|  
|[CArchive::ReadString](#readstring)|単一行のテキストを読み取ります。|  
|[CArchive::SerializeClass](#serializeclass)|読み取りまたは書き込みクラスの参照を`CArchive`オブジェクトの方向に応じて、`CArchive`です。|  
|[CArchive::SetLoadParams](#setloadparams)|読み込みの配列が拡張サイズを設定します。 任意のオブジェクトが読み込まれる前に、または前に呼び出す必要があります`MapObject`または`ReadObject`が呼び出されます。|  
|[CArchive::SetObjectSchema](#setobjectschema)|アーカイブ オブジェクトに格納されているオブジェクトのスキーマを設定します。|  
|[CArchive::SetStoreParams](#setstoreparams)|ハッシュ テーブルのサイズと、シリアル化プロセス中に一意のオブジェクトを識別するために使用するマップのブロック サイズを設定します。|  
|[CArchive::Write](#write)|生のバイトを書き込みます。|  
|[CArchive::WriteClass](#writeclass)|参照を書き込み、`CRuntimeClass`に、`CArchive`です。|  
|[CArchive::WriteObject](#writeobject)|オブジェクトの`Serialize`を格納するための関数です。|  
|[CArchive::WriteString](#writestring)|単一行のテキストを書き込みます。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CArchive::operator&lt;&lt;](#operator_lt_lt)|オブジェクトと、アーカイブにプリミティブ型を格納します。|  
|[CArchive::operator&gt;&gt;](#operator_gt_gt)|アーカイブからのオブジェクト、プリミティブ型を読み込みます。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CArchive::m_pDocument](#m_pdocument)||  
  
## <a name="remarks"></a>コメント  
 `CArchive`基本クラスはありません。  
  
 後でメモリに保持して再構築永続的なストレージからオブジェクトを読み込むことができます。 データを永続的なは、このプロセスは「シリアル化します。"と呼ばれる  
  
 アーカイブ オブジェクトをバイナリ ストリームの種類として考えることができます。 入力/出力ストリームと同様に、アーカイブがファイルに関連付けられ、バッファー内の書き込みと記憶域との間のデータの読み取りが許可されます。 入力/出力ストリームは、ASCII 文字のシーケンスを処理しますが、アーカイブが効率的な非冗長形式でバイナリ オブジェクト データを処理します。  
  
 作成する必要があります、 [CFile](../../mfc/reference/cfile-class.md)オブジェクトを作成する前に、`CArchive`オブジェクトです。 さらに、アーカイブの読み込み/ストアの状態がファイルのオープン モードと互換性があることを確認する必要があります。 1 つのアクティブなアーカイブ ファイルごとに制限されます。  
  
 構築する場合、`CArchive`オブジェクト、クラスのオブジェクトにアタッチする`CFile`(または派生クラス) を表すファイルを開く。 また、アーカイブを読み込み、または格納用に使用するかどうかも指定します。 A`CArchive`プリミティブ型だけでなく、オブジェクトのオブジェクトを処理できる[CObject](../../mfc/reference/cobject-class.md)の派生クラスをシリアル化のために設計されています。 シリアル化可能なクラスには通常、`Serialize`メンバー関数とそれが通常使用して、 [DECLARE_SERIAL](../../mfc/reference/run-time-object-model-services.md#declare_serial)と[IMPLEMENT_SERIAL](../../mfc/reference/run-time-object-model-services.md#implement_serial)マクロ、クラスの下の手順に従って`CObject`します。  
  
 オーバー ロードされた抽出 ( ** >> **) または挿入を行う ( ** << **) 演算子は、両方のプリミティブ型をサポートするプログラミング インターフェイスの便利なアーカイブおよび`CObject`-クラスを派生します。  
  
 `CArchive`Windows ソケットの MFC クラスを使用したプログラミングでは[CSocket](../../mfc/reference/csocket-class.md)と[CSocketFile](../../mfc/reference/csocketfile-class.md)します。 [時](#isbufferempty)メンバー関数は、その使用状況をサポートしています。  
  
 詳細については`CArchive`、記事を参照して[シリアル化](../../mfc/serialization-in-mfc.md)と[Windows ソケット: アーカイブ付きソケットの使用](../../mfc/windows-sockets-using-sockets-with-archives.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `CArchive`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afx.h  
  
##  <a name="abort"></a>CArchive::Abort  
 この関数を呼び出して例外をスローせずに、アーカイブを閉じます。  
  
```  
void Abort ();
```  
  
### <a name="remarks"></a>コメント  
 **CArchive**デストラクターは通常どおり呼び出します**閉じる**、保存されていないすべてのデータを消去するされますに関連付けられた`CFile`オブジェクトです。 これにより、例外が発生します。  
  
 使用することをお勧めはこれらの例外をキャッチするときに**中止**、破棄されるように、`CArchive`オブジェクトな例外が発生します。 例外を処理するときに`CArchive::Abort`ために、エラーに関する例外をスローしませんとは異なり、 [CArchive::Close](#close)、**中止**エラーは無視されます。  
  
 使用した場合**新しい**を割り当てる、`CArchive`ヒープのオブジェクトの後に、ファイルを閉じて後に削除する必要があります。  
  
### <a name="example"></a>例  
  例を参照してください[CArchive::WriteClass](#writeclass)します。  
  
##  <a name="carchive"></a>CArchive::CArchive  
 構築、`CArchive`オブジェクトを読み込み、またはオブジェクトの格納に使用するかどうかを指定します。  
  
```  
CArchive(
    CFile* pFile,  
    UINT nMode,  
    int nBufSize = 4096,  
    void* lpBuf = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `pFile`  
 ポインター、`CFile`最終的な送信元または永続的なデータの転送先であるオブジェクト。  
  
 `nMode`  
 オブジェクトをから読み込まれるか、アーカイブに格納されているかどうかを指定するフラグ。 `nMode`パラメーターには、次の値のいずれかが必要があります。  
  
- **CArchive::load**アーカイブからデータを読み込みます。 必要なだけ`CFile`の読み取りアクセス許可。  
  
- **CArchive::store**データをアーカイブに保存します。 必要と`CFile`の書き込みアクセス許可。  
  
- **CArchive::bNoFlushOnDelete**から自動的に呼び出すことにより、アーカイブ`Flush`アーカイブ デストラクターが呼び出されたとき。 このフラグを設定する場合を明示的に呼び出す責任が**閉じる**デストラクターが呼び出される前にします。 そうしないと、データが破損します。  
  
 `nBufSize`  
 内部ファイル バッファーのサイズをバイト単位で指定する整数。 既定のバッファー サイズは 4,096 バイトであることに注意してください。 ラージ オブジェクトを定期的にアーカイブする場合は、ファイルのバッファー サイズの倍数では大きなバッファー サイズを使用する場合にパフォーマンスが改善されます。  
  
 `lpBuf`  
 ユーザーが指定したサイズのバッファーへの省略可能なポインター`nBufSize`します。 このパラメーターを指定しない場合、アーカイブがバッファーがローカル ヒープから割り当てられ、オブジェクトが破棄されるときに、それを解放します。 アーカイブは、ユーザーが指定したバッファーを解放しません。  
  
### <a name="remarks"></a>コメント  
 アーカイブを作成した後は、この仕様を変更できません。  
  
 使用することは`CFile`アーカイブを終了するまで、ファイルの状態を変更する操作。 このような操作には、アーカイブの整合性が破損します。 アーカイブのファイル オブジェクトを取得することによってシリアル化中にいつでもファイル ポインターの位置にアクセスすることがあります、 [GetFile](#getfile)メンバー関数を使用して、[実行](../../mfc/reference/cfile-class.md#getposition)関数です。 呼び出す必要があります[ときは](#flush)ファイル ポインターの位置を取得する前にします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCSerialization&#12;](../../mfc/codesnippet/cpp/carchive-class_1.cpp)]  
  
##  <a name="close"></a>CArchive::Close  
 バッファーに残っているデータをフラッシュし、アーカイブを閉じ、ファイルからアーカイブを切断します。  
  
```  
void Close();
```  
  
### <a name="remarks"></a>コメント  
 アーカイブで他の操作が許可されていません。 アーカイブを閉じると、同じファイルに対して別のアーカイブを作成するまたはファイルを閉じることができます。  
  
 メンバー関数は、**閉じる**によりすべてのデータがアーカイブからファイルに転送され、アーカイブを使用できなくなります。 ファイルから、ストレージ メディアへの転送を完了する必要があります最初に使用する[先](../../mfc/reference/cfile-class.md#close)し、破棄、`CFile`オブジェクトです。  
  
### <a name="example"></a>例  
  例を参照してください[CArchive::WriteString](#writestring)します。  
  
##  <a name="flush"></a>ときは  
 ファイルに書き込まれるアーカイブ バッファーの残りの部分を強制します。  
  
```  
void Flush();
```  
  
### <a name="remarks"></a>コメント  
 メンバー関数は、`Flush`アーカイブからファイルへのすべてのデータが転送されることを確認します。 呼び出す必要があります[先](../../mfc/reference/cfile-class.md#close)ストレージ メディアには、ファイルからの転送を完了します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCSerialization&#13;](../../mfc/codesnippet/cpp/carchive-class_2.cpp)]  
  
##  <a name="getfile"></a>CArchive::GetFile  
 取得、`CFile`このアーカイブ対象のオブジェクトのポインター。  
  
```  
CFile* GetFile() const;  
```  
  
### <a name="return-value"></a>戻り値  
 定数ポインター、`CFile`使用中のオブジェクト。  
  
### <a name="remarks"></a>コメント  
 使用する前に、アーカイブをフラッシュする必要があります`GetFile`します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCSerialization&#14;](../../mfc/codesnippet/cpp/carchive-class_3.cpp)]  
  
##  <a name="getobjectschema"></a>CArchive::GetObjectSchema  
 この関数から呼び出す、`Serialize`関数が現在逆シリアル化するオブジェクトのバージョンを決定します。  
  
```  
UINT GetObjectSchema();
```  
  
### <a name="return-value"></a>戻り値  
 逆シリアル化、読み取られているオブジェクトのバージョン。  
  
### <a name="remarks"></a>コメント  
 この関数を呼び出す場合のみを有効な`CArchive`オブジェクトが読み込まれる ([とき](#isloading)0 以外を返します)。 最初の呼び出しをする必要があります、`Serialize`関数と呼び出し先の&1; 回だけ出現します。 戻り値 ( **UINT**) –&1; は、バージョン番号が不明であることを示します。  
  
 A `CObject`-派生クラスを使用ことがあります**VERSIONABLE_SCHEMA**結合 (ビット演算子を使用して`OR`) 自体スキーマ バージョンと (で、`IMPLEMENT_SERIAL`マクロ) オブジェクトを作成する、"バージョン管理が可能"は、オブジェクトが`Serialize`メンバー関数は、複数のバージョンを読み取ることができます。 既定のフレームワーク機能 (せず**VERSIONABLE_SCHEMA**) は、バージョンが一致していないときに例外をスローする方法です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCSerialization&#15;](../../mfc/codesnippet/cpp/carchive-class_4.cpp)]  
  
##  <a name="isbufferempty"></a>CArchive::IsBufferEmpty  
 アーカイブ オブジェクトの内部バッファーが空かどうかを判断するには、このメンバー関数を呼び出します。  
  
```  
BOOL IsBufferEmpty() const;  
```  
  
### <a name="return-value"></a>戻り値  
 アーカイブのバッファーが空である場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 Windows ソケットの MFC クラスを使用したプログラミングをサポートするためにこの関数に渡された`CSocketFile`です。 関連付けられているアーカイブに使用する必要はありません、`CFile`オブジェクトです。  
  
 使用する理由`IsBufferEmpty`に関連付けられているアーカイブを使用して、`CSocketFile`オブジェクトが&1; つ以上のメッセージまたはレコード、アーカイブのバッファーが含まれるあります。 1 つのメッセージを受信した後を使用する必要があります`IsBufferEmpty`バッファーが空になるまでデータの受信を継続するループを制御します。 詳細については、次を参照してください。、[受信](../../mfc/reference/casyncsocket-class.md#receive)クラスのメンバー関数`CAsyncSocket`、を使用する方法を説明`IsBufferEmpty`します。  
  
 詳細については、次を参照してください。 [Windows ソケット: アーカイブ付きソケットの使用](../../mfc/windows-sockets-using-sockets-with-archives.md)します。  
  
##  <a name="isloading"></a>場合  
 アーカイブがデータを読み込んでいるかどうかを決定します。  
  
```  
BOOL IsLoading() const;  
```  
  
### <a name="return-value"></a>戻り値  
 アーカイブが現在読み込み用に使用されている場合は 0 以外それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 によって呼び出されます、`Serialize`アーカイブ済みのクラスの関数です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCSerialization&#16;](../../mfc/codesnippet/cpp/carchive-class_5.cpp)]  
  
##  <a name="isstoring"></a>用  
 アーカイブがデータを格納するかどうかを決定します。  
  
```  
BOOL IsStoring() const;  
```  
  
### <a name="return-value"></a>戻り値  
 アーカイブが現在; を格納するために使用されている場合は 0 以外それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 によって呼び出されます、`Serialize`アーカイブ済みのクラスの関数です。  
  
 場合、`IsStoring`アーカイブの状態が 0 以外で、その`IsLoading`の状態は 0、またはその逆です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCSerialization&17;](../../mfc/codesnippet/cpp/carchive-class_6.cpp)]  
  
##  <a name="mapobject"></a>CArchive::MapObject  
 実際に、ファイルにシリアル化されませんマップ内のオブジェクトを配置するには、このメンバー関数を呼び出しますが、参照のサブオブジェクトとして提供されます。  
  
```  
void MapObject(const CObject* pOb);
```  
  
### <a name="parameters"></a>パラメーター  
 `pOb`  
 格納されているオブジェクトへの定数ポインター。  
  
### <a name="remarks"></a>コメント  
 たとえば、ドキュメントをシリアル化がありますが、ドキュメントの一部である項目をシリアル化します。 呼び出して`MapObject`、それらのアイテム、または下位オブジェクトには、ドキュメントを参照することができます。 シリアル化されたサブ項目をシリアル化できるさらに、その`m_pDocument`バック ポインター。  
  
 呼び出すことができます`MapObject`に格納しからの読み込み、`CArchive`オブジェクトです。 `MapObject`管理されている内部データ構造を指定したオブジェクトを追加、`CArchive`オブジェクトのシリアル化および逆シリアル化中とは異なり[ReadObject](#readobject)と[WriteObject](#writeobject)**、**は呼び出しませんオブジェクトのシリアル化します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCSerialization&#18;](../../mfc/codesnippet/cpp/carchive-class_7.h)]  
  
 [!code-cpp[NVC_MFCSerialization&#19;](../../mfc/codesnippet/cpp/carchive-class_8.cpp)]  
  
 [!code-cpp[NVC_MFCSerialization&#20;](../../mfc/codesnippet/cpp/carchive-class_9.h)]  
  
 [!code-cpp[NVC_MFCSerialization #&21;](../../mfc/codesnippet/cpp/carchive-class_10.cpp)]  
  
##  <a name="m_pdocument"></a>CArchive::m_pDocument  
 設定**NULL**既定では、このポインターを**CDocument**のユーザーに何かに設定できる、`CArchive`要望をインスタンス化します。  
  
```  
CDocument* m_pDocument;  
```  
  
### <a name="remarks"></a>コメント  
 This ポインターの一般的な使用方法では、シリアル化されているすべてのオブジェクトにシリアル化プロセスに関する追加情報を伝えるためです。 ドキュメントにポインターを初期化することによりこれは、(、 **CDocument**の派生クラス) をシリアル化される、ドキュメント内のオブジェクトも、必要な場合に、ドキュメントをアクセスできるようにします。 このポインターはでも使用`COleClientItem`シリアル化中にオブジェクトです。  
  
 Framework セット`m_pDocument`ユーザーがファイルを発行するときにシリアル化されるドキュメントを開くか、コマンドを保存します。 明示的に設定する必要がありますが、Object Linking and Embedding (OLE) コンテナーのドキュメント ファイルを開くまたは保存以外の理由をシリアル化する場合`m_pDocument`します。 たとえばはこれを行うをクリップボードにコンテナー ドキュメントをシリアル化するとします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCSerialization&#35;](../../mfc/codesnippet/cpp/carchive-class_11.cpp)]  
  
##  <a name="operator_lt_lt"></a>CArchive::operator&lt;&lt;  
 指定したオブジェクトまたはプリミティブ型、アーカイブを格納します。  
  
```  
friend CArchive& operator<<(
    CArchive& ar,  
    const CObject* pOb);

 
throw(
    CArchiveException*, 
    CFileException*);

 
CArchive& AFXAPI operator<<(
    CArchive& ar,  
    const RECT& rect);

 
CArchive& AFXAPI operator<<(
    CArchive& ar,  
    POINT point);

 
CArchive& AFXAPI operator<<(
    CArchive& ar,  
    SIZE size);

 
template<typename BaseType,  
    class StringTraits> CArchive& operator<<(
    const ATL::CStringT<BaseType,  
    StringTraits>& str);  
  
CArchive& operator<<(BYTE by); 
CArchive& operator<<(WORD w); 
CArchive& operator<<(LONG l); 
CArchive& operator<<(DWORD dw); 
CArchive& operator<<(float f); 
CArchive& operator<<(double d); 
CArchive& operator<<(int i); 
CArchive& operator<<(short w); 
CArchive& operator<<(char ch); 
CArchive& operator<<(wchar_t ch); 
CArchive& operator<<(unsigned u); 
CArchive& operator<<(bool b); 
CArchive& operator<<(ULONGLONG dwdw); 
CArchive& operator<<(LONGLONG dwdw);
```  
  
### <a name="return-value"></a>戻り値  
 A`CArchive`を&1; 行に複数の挿入演算子を有効に参照します。  
  
### <a name="remarks"></a>コメント  
 上記の最後の 2 つのバージョンは、64 ビット整数値を格納するためには、具体的にです。  
  
 使用した場合、`IMPLEMENT_SERIAL`クラスの実装のオーバー ロードされた挿入演算子にマクロ`CObject`、保護された呼び出し**WriteObject**します。 この関数を呼び出す、`Serialize`クラスの関数です。  
  
 [CStringT](../../atl-mfc-shared/reference/cstringt-class.md)挿入演算子 (<) supports diagnostic dumping and storing to an archive. supports="" diagnostic="" dumping="" and="" storing="" to="" an=""></) supports diagnostic dumping and storing to an archive.>  
  
### <a name="example"></a>例  
 この例では、使用、`CArchive`挿入演算子< with="" the="">`int`と`long`型です。  
  
 [!code-cpp[NVC_MFCSerialization #&31;](../../mfc/codesnippet/cpp/carchive-class_12.cpp)]  
  
### <a name="example"></a>例  
 この例 2 では、使用、`CArchive`挿入演算子< with="" the="">`CStringT`型です。  
  
 [!code-cpp[NVC_MFCSerialization&#32;](../../mfc/codesnippet/cpp/carchive-class_13.cpp)]  
  
##  <a name="operator_gt_gt"></a>CArchive::operator&gt;&gt;  
 アーカイブから指定したオブジェクトまたはプリミティブ型を読み込みます。  
  
```  
friend CArchive& operator>>(
    CArchive& ar,  
    CObject *& pOb);

 
throw(
    CArchiveException*, 
    CFileException*, 
    CMemoryException*);

 
friend CArchive& operator>>(
    CArchive& ar,  
    const CObject *& pOb);

 
throw(
    CArchiveException*, 
    CFileException*, 
    CMemoryException*);

 
CArchive& AFXAPI operator>>(
    CArchive& ar,  
    const RECT& rect);

 
CArchive& AFXAPI operator>>(
    CArchive& ar,  
    POINT point);

 
CArchive& AFXAPI operator>>(
    CArchive& ar,  
    SIZE size);

 
template<typename BaseType,  
    class StringTraits> CArchive& operator>>(
    ATL::CStringT<BaseType, 
    StringTraits>& str);  
  
CArchive& operator>>(BYTE& by);    
CArchive& operator>>(WORD& w);    
CArchive& operator>>(int& i);    
CArchive& operator>>(LONG& l);    
CArchive& operator>>(DWORD& dw);    
CArchive& operator>>(float& f);    
CArchive& operator>>(double& d);    
CArchive& operator>>(short& w);    
CArchive& operator>>(char& ch);    
CArchive& operator>>(wchar_t& ch);    
CArchive& operator>>(unsigned& u);    
CArchive& operator>>(bool& b);    
CArchive& operator>>(ULONGLONG& dwdw);   
CArchive& operator>>(LONGLONG& dwdw);
```  
  
### <a name="return-value"></a>戻り値  
 A`CArchive`を&1; 行に複数の抽出演算子を有効に参照します。  
  
### <a name="remarks"></a>コメント  
 上記の最後の 2 つのバージョンは、64 ビット整数値を読み込むためには、具体的にです。  
  
 使用した場合、`IMPLEMENT_SERIAL`クラスの実装し、過負荷になって抽出演算子でマクロ`CObject`、保護された呼び出し**ReadObject** (0 以外のランタイム クラスのポインター) を持つ関数です。 この関数を呼び出す、`Serialize`クラスの関数です。  
  
 [CStringT](../../atl-mfc-shared/reference/cstringt-class.md)抽出演算子 (>) は、アーカイブからの読み込みをサポートしています。  
  
### <a name="example"></a>例  
 この例では、使用、`CArchive`抽出演算子 >> で、`int`型です。  
  
 [!code-cpp[NVC_MFCSerialization #&33;](../../mfc/codesnippet/cpp/carchive-class_14.cpp)]  
  
### <a name="example"></a>例  
 この例では、使用、`CArchive`挿入および抽出演算子\<と >> で、`CStringT`型です。  
  
 [!code-cpp[NVC_MFCSerialization #&34;](../../mfc/codesnippet/cpp/carchive-class_15.cpp)]  
  
##  <a name="read"></a>読み書きするとき  
 アーカイブから指定したバイト数を読み取ります。  
  
```  
UINT Read(void* lpBuf, UINT nMax);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpBuf`  
 アーカイブから読み取られたデータを受信するユーザーが指定したバッファーへのポインター。  
  
 `nMax`  
 アーカイブから読み取るバイト数を指定する符号なし整数。  
  
### <a name="return-value"></a>戻り値  
 実際に読み取るバイト数を表す符号なし整数。 戻り値が要求された数よりも小さい場合は、ファイルの末尾に達しています。 ファイルの末尾の条件では、例外はスローされません。  
  
### <a name="remarks"></a>コメント  
 アーカイブは、バイト数を解釈できません。  
  
 使用することができます、**読み取り**内のメンバー関数、`Serialize`オブジェクトに含まれている通常の構造を読み取るための関数です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCSerialization #&24;](../../mfc/codesnippet/cpp/carchive-class_16.cpp)]  
  
##  <a name="readclass"></a>場合  
 このメンバー関数を呼び出して以前に保存されているクラスへの参照を読み取る[WriteClass](#writeclass)します。  
  
```  
CRuntimeClass* ReadClass(
    const CRuntimeClass* pClassRefRequested = NULL,  
    UINT* pSchema = NULL,  
    DWORD* pObTag = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `pClassRefRequested`  
 ポインター、 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)要求クラスの参照に対応する構造体。 できる**NULL**します。  
  
 `pSchema`  
 以前に格納されているランタイム クラスのスキーマへのポインター。  
  
 `pObTag`  
 オブジェクトの一意のタグを表す数値。 実装で内部的に使用される[ReadObject](#readobject)します。 高度なプログラミングだけです。`pObTag`通常べき**NULL**します。  
  
### <a name="return-value"></a>戻り値  
 ポインター、 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)構造体。  
  
### <a name="remarks"></a>コメント  
 場合`pClassRefRequested`は**NULL**、`ReadClass`アーカイブされたクラスの情報がランタイム クラスと互換性があることを確認します。 互換性がない場合`ReadClass`をスローする[CArchiveException](../../mfc/reference/carchiveexception-class.md)します。  
  
 ランタイム クラスを使用する必要があります[DECLARE_SERIAL](../../mfc/reference/run-time-object-model-services.md#declare_serial)と[IMPLEMENT_SERIAL](../../mfc/reference/run-time-object-model-services.md#implement_serial)。 そうしないと、`ReadClass`はをスロー、[行わない](../../mfc/reference/cnotsupportedexception-class.md)します。  
  
 場合`pSchema`は**NULL**、ストアド クラスのスキーマを呼び出すことによって取得できます[CArchive::GetObjectSchema](#getobjectschema)。 そうしないと、 ** \* ** `pSchema`は保存されていたのランタイム クラスのスキーマが含まれます。  
  
 使用する[SerializeClass](#serializeclass)の代わりに`ReadClass`、読み取りと書き込みの両方のクラスの参照を処理します。  
  
### <a name="example"></a>例  
  例を参照してください[CArchive::WriteClass](#writeclass)します。  
  
##  <a name="readobject"></a>CArchive::ReadObject  
 アーカイブからオブジェクト データを読み込んで、適切な型のオブジェクトを構築します。  
  
```  
CObject* ReadObject(const CRuntimeClass* pClass);
```  
  
### <a name="parameters"></a>パラメーター  
 `pClass`  
 定数ポインター、 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)を読み込む予定がオブジェクトに対応する構造体。  
  
### <a name="return-value"></a>戻り値  
 A [CObject](../../mfc/reference/cobject-class.md)を使用して派生クラスを正しいに安全にキャストする必要がありますポインター[使うため](../../mfc/reference/cobject-class.md#iskindof)です。  
  
### <a name="remarks"></a>コメント  
 通常、この関数は呼び出される、`CArchive`抽出 ( ** >> **) のオーバー ロードされた演算子、 [CObject](../../mfc/reference/cobject-class.md)ポインター。 **ReadObject**を呼び出す、`Serialize`アーカイブ済みのクラスの関数です。  
  
 0 以外を指定する場合は、`pClass`ことによって取得されるパラメーター、 [RUNTIME_CLASS](../../mfc/reference/run-time-object-model-services.md#runtime_class)マクロ、関数は、アーカイブ済みのオブジェクトのランタイム クラスを検証します。 これは、場合、使用していること、`IMPLEMENT_SERIAL`マクロで、クラスの実装です。  
  
### <a name="example"></a>例  
  例を参照してください[CArchive::WriteObject](#writeobject)します。  
  
##  <a name="readstring"></a>CArchive::ReadString  
 関連付けられているファイルからバッファーにテキスト データを読み取るには、このメンバー関数を呼び出す、`CArchive`オブジェクトです。  
  
```  
BOOL ReadString(CString& rString); 
LPTSTR ReadString(LPTSTR lpsz, UINT nMax);
```  
  
### <a name="parameters"></a>パラメーター  
 `rString`  
 参照、 [CString](../../atl-mfc-shared/reference/cstringt-class.md) CArchive オブジェクトに関連付けられているファイルから読み取られた後、結果の文字列が含まれる。  
  
 `lpsz`  
 Null で終わる文字列を受信するユーザーが指定したバッファーへのポインターを指定します。  
  
 `nMax`  
 読み取る文字の最大数を指定します。 いずれかを指定する必要がありますのサイズよりも小さいか、 *lpsz*バッファー。  
  
### <a name="return-value"></a>戻り値  
 取得するバージョンで**BOOL**、 **TRUE**成功した場合**FALSE**それ以外の場合。  
  
 取得するバージョンでは、 `LPTSTR`、テキスト データを格納しているバッファーへのポインター**NULL**ファイルの終端に達した場合。  
  
### <a name="remarks"></a>コメント  
 メンバー関数のバージョンで、`nMax`パラメーター バッファーを保持するに制限`nMax`- 1 文字です。 復帰と改行のペアでは、読み取りが停止します。 後続の改行文字は常に削除します。 いずれの場合は、null 文字 ('\0') が追加されます。  
  
 [読み書きするとき](#read)は復帰と改行のペアでテキスト モードの入力が、それを終了しないにも使用できます。  
  
### <a name="example"></a>例  
  例を参照してください[CArchive::WriteString](#writestring)します。  
  
##  <a name="serializeclass"></a>CArchive::SerializeClass  
 基本クラスのバージョン情報に格納したりする場合は、このメンバー関数を呼び出します。  
  
```  
void SerializeClass(const CRuntimeClass* pClassRef);
```  
  
### <a name="parameters"></a>パラメーター  
 `pClassRef`  
 基本クラスのランタイム クラス オブジェクトへのポインター。  
  
### <a name="remarks"></a>コメント  
 `SerializeClass`読み取りまたは書き込みにクラスへの参照が、`CArchive`の方向に応じて、オブジェクト、`CArchive`です。 使用`SerializeClass`の代わりに[ReadClass](#readclass)と[WriteClass](#writeclass)基底クラスのオブジェクトをシリアル化する便利な方法として`SerializeClass`より少ないコードと以下のパラメーターが必要です。  
  
 ような`ReadClass`、`SerializeClass`アーカイブされたクラスの情報がランタイム クラスと互換性があることを確認します。 互換性がない場合`SerializeClass`をスローする[CArchiveException](../../mfc/reference/carchiveexception-class.md)します。  
  
 ランタイム クラスを使用する必要があります[DECLARE_SERIAL](../../mfc/reference/run-time-object-model-services.md#declare_serial)と[IMPLEMENT_SERIAL](../../mfc/reference/run-time-object-model-services.md#implement_serial)。 そうしないと、`SerializeClass`はをスロー、[行わない](../../mfc/reference/cnotsupportedexception-class.md)します。  
  
 使用して、 [RUNTIME_CLASS](../../mfc/reference/run-time-object-model-services.md#runtime_class)マクロの値を取得する、`pRuntimeClass`パラメーター。 基本クラスを使用する必要がありますが、 [IMPLEMENT_SERIAL](../../mfc/reference/run-time-object-model-services.md#implement_serial)マクロです。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCSerialization&#25;](../../mfc/codesnippet/cpp/carchive-class_17.h)]  
  
##  <a name="setloadparams"></a>CArchive::SetLoadParams  
 呼び出す`SetLoadParams`としようとして読み取りの数が多い`CObject`-アーカイブから派生したオブジェクト。  
  
```  
void SetLoadParams(UINT nGrowBy = 1024);
```  
  
### <a name="parameters"></a>パラメーター  
 `nGrowBy`  
 サイズの増加が必要な場合を確保する要素のスロットの最小数。  
  
### <a name="remarks"></a>コメント  
 `CArchive`アーカイブに格納されているオブジェクトへの参照を解決するのには、読み込み配列を使用します。 `SetLoadParams`読み込みの配列が拡張サイズを設定できます。  
  
 呼び出す必要はありません`SetLoadParams`任意のオブジェクトが読み込まれた後、または後[MapObject](#mapobject)または[ReadObject](#readobject)が呼び出されます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCSerialization #&26;](../../mfc/codesnippet/cpp/carchive-class_18.h)]  
  
##  <a name="setobjectschema"></a>CArchive::SetObjectSchema  
 アーカイブ オブジェクトに格納されているオブジェクトのスキーマを設定するには、このメンバー関数を呼び出す`nSchema`します。  
  
```  
void SetObjectSchema(UINT nSchema);
```  
  
### <a name="parameters"></a>パラメーター  
 `nSchema`  
 オブジェクトのスキーマを指定します。  
  
### <a name="remarks"></a>コメント  
 次の呼び出し[使い方](#getobjectschema)に格納された値を返す`nSchema`します。  
  
 使用`SetObjectSchema`の高度なバージョン管理; などの場合で読み取られる特定のバージョンを強制的に、`Serialize`派生クラスの関数です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCSerialization #&27;](../../mfc/codesnippet/cpp/carchive-class_19.cpp)]  
  
##  <a name="setstoreparams"></a>CArchive::SetStoreParams  
 使用`SetStoreParams`の数が多いを格納するときに`CObject`-アーカイブ内のオブジェクトを派生します。  
  
```  
void SetStoreParams(UINT nHashSize = 2053, UINT nBlockSize = 128);
```  
  
### <a name="parameters"></a>パラメーター  
 *nHashSize*  
 インターフェイス ポインターのハッシュ テーブルのサイズにマップします。 素数をする必要があります。  
  
 `nBlockSize`  
 パラメーターを拡張するためのメモリ割り当ての粒度を指定します。 最適なパフォーマンスの 2 のべき乗である必要があります。  
  
### <a name="remarks"></a>コメント  
 `SetStoreParams`ハッシュ テーブルのサイズと、シリアル化プロセス中に一意のオブジェクトを識別するために使用するマップのブロック サイズを設定できます。  
  
 呼び出す必要はありません`SetStoreParams`すべてのオブジェクトが格納された後、または後[MapObject](#mapobject)または[WriteObject](#writeobject)が呼び出されます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCSerialization #&26;](../../mfc/codesnippet/cpp/carchive-class_18.h)]  
  
##  <a name="write"></a>CArchive::Write  
 指定したバイト数をアーカイブに書き込みます。  
  
```  
void Write(const void* lpBuf, INT nMax);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpBuf`  
 アーカイブに書き込まれるデータを格納しているユーザーが指定したバッファーへのポインター。  
  
 `nMax`  
 アーカイブに書き込まれるバイト数を指定する整数。  
  
### <a name="remarks"></a>コメント  
 アーカイブのバイトをフォーマットしません。  
  
 使用することができます、**書き込み**内のメンバー関数、`Serialize`オブジェクトに通常の構造を記述する関数が含まれています。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCSerialization 第&23;](../../mfc/codesnippet/cpp/carchive-class_20.cpp)]  
  
##  <a name="writeclass"></a>CArchive::WriteClass  
 使用`WriteClass`派生クラスのシリアル化中に基底クラスのバージョンとクラス情報を格納します。  
  
```  
void WriteClass(const CRuntimeClass* pClassRef);
```  
  
### <a name="parameters"></a>パラメーター  
 `pClassRef`  
 ポインター、 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)要求クラスの参照に対応する構造体。  
  
### <a name="remarks"></a>コメント  
 `WriteClass`参照を書き込み、 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 、基本クラスに対する、`CArchive`です。 使用[場合](#readclass)参照を取得します。  
  
 `WriteClass`アーカイブ済みのクラスの情報にランタイム クラスに互換性があることを確認します。 互換性がない場合`WriteClass`をスローする[CArchiveException](../../mfc/reference/carchiveexception-class.md)します。  
  
 ランタイム クラスを使用する必要があります[DECLARE_SERIAL](../../mfc/reference/run-time-object-model-services.md#declare_serial)と[IMPLEMENT_SERIAL](../../mfc/reference/run-time-object-model-services.md#implement_serial)。 そうしないと、`WriteClass`はをスロー、[行わない](../../mfc/reference/cnotsupportedexception-class.md)します。  
  
 使用する[SerializeClass](#serializeclass)の代わりに`WriteClass`、読み取りと書き込みの両方のクラスの参照を処理します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCSerialization #&28;](../../mfc/codesnippet/cpp/carchive-class_21.cpp)]  
  
##  <a name="writeobject"></a>CArchive::WriteObject  
 指定した格納`CObject`をアーカイブします。  
  
```  
void WriteObject(const CObject* pOb);
```  
  
### <a name="parameters"></a>パラメーター  
 `pOb`  
 格納されているオブジェクトへの定数ポインター。  
  
### <a name="remarks"></a>コメント  
 通常、この関数は呼び出される、`CArchive`カーソル ( ** << **) の演算子はオーバー ロード`CObject`します。 **WriteObject**を呼び出す、`Serialize`アーカイブ済みのクラスの関数です。  
  
 使用する必要があります、`IMPLEMENT_SERIAL`マクロ アーカイブを有効にします。 **WriteObject** ASCII クラス名をアーカイブに書き込みます。 このクラス名は、読み込みプロセス中に後で検証されます。 特殊なエンコード スキームでは、クラスの複数のオブジェクトのクラス名の不必要な重複を防ぎます。 このスキームでは、1 つ以上のポインターの対象となるオブジェクトの冗長ストレージも回避されます。  
  
 正確なオブジェクトのエンコーディング (ASCII クラス名の有無を含む) 方法は、実装の詳細し、後で、ライブラリのバージョンで変更できます。  
  
> [!NOTE]
>  作成、削除、およびアーカイブして開始する前に、すべてのオブジェクトの更新を完了します。 オブジェクトの変更のアーカイブが混在する場合、アーカイブは破損しています。  
  
### <a name="example"></a>例  
 クラスの定義の`CAge`の例を参照してください[使われて](../../mfc/reference/coblist-class.md#coblist)します。  
  
 [!code-cpp[NVC_MFCSerialization #&29;](../../mfc/codesnippet/cpp/carchive-class_22.cpp)]  
  
##  <a name="writestring"></a>CArchive::WriteString  
 このメンバー関数を使用してバッファーからデータを関連付けられたファイルを書き込む、`CArchive`オブジェクトです。  
  
```  
void WriteString(LPCTSTR lpsz);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpsz`  
 Null で終わる文字列を格納するバッファーへのポインターを指定します。  
  
### <a name="remarks"></a>コメント  
 終端の null 文字 ('\0') は、ファイルに書き込まれませんまた、改行を配置に自動的に書き込まれます。  
  
 `WriteString`ディスクの空き容量の条件を含むいくつかの条件への応答で例外をスローします。  
  
 **書き込み**も利用できますが、null 文字で終了してではなく、ファイルに要求されたバイト数を書き込まれるが、します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCSerialization #&30;](../../mfc/codesnippet/cpp/carchive-class_23.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [CFile クラス](../../mfc/reference/cfile-class.md)   
 [CObject クラス](../../mfc/reference/cobject-class.md)   
 [CSocket クラス](../../mfc/reference/csocket-class.md)   
 [CSocketFile クラス](../../mfc/reference/csocketfile-class.md)

