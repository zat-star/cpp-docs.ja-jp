---
title: "CDaoException クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDaoException
dev_langs:
- C++
helpviewer_keywords:
- errors [C++], DAO
- CDaoException class
- DAO (Data Access Objects), exceptions
- exceptions, in MFC DAO classes
- Errors collection, DAO
- collections, DAO errors
ms.assetid: b2b01fa9-7ce2-42a1-842e-40f13dc50da4
caps.latest.revision: 24
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: d1cb1c6dbe50d383981af03cc97d1977be12a5f6
ms.lasthandoff: 02/24/2017

---
# <a name="cdaoexception-class"></a>CDaoException クラス
データ アクセス オブジェクト (DAO: Data Accsess Object) を基にした MFC データベース クラスから発生する例外条件を表します。  
  
## <a name="syntax"></a>構文  
  
```  
class CDaoException : public CException  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CDaoException::CDaoException](#cdaoexception)|`CDaoException` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[あります。](#geterrorcount)|データベース エンジンのエラーのコレクション内には、エラーの数を返します。|  
|[CDaoException::GetErrorInfo](#geterrorinfo)|エラーのコレクション内には、特定のエラー オブジェクトに関するエラー情報を返します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CDaoException::m_nAfxDaoError](#m_nafxdaoerror)|MFC DAO クラスで何らかのエラーの拡張エラー コードが含まれています。|  
|[CDaoException::m_pErrorInfo](#m_perrorinfo)|ポインター、 [CDaoErrorInfo](../../mfc/reference/cdaoerrorinfo-structure.md) DAO エラーの&1; つのオブジェクトに関する情報を含むオブジェクト。|  
|[CDaoException::m_scode](#m_scode)|[SCODE](#m_scode)エラーに関連付けられた値。|  
  
## <a name="remarks"></a>コメント  
 クラスには、例外の原因を調べて使用できるパブリック データ メンバーが含まれます。 `CDaoException`オブジェクトが構築され、DAO データベース クラスのメンバー関数によってスローされます。  
  
> [!NOTE]
>  DAO データベース クラスは、ODBC Open Database Connectivity () を基 MFC データベース クラスとは異なります。 DAO データベース クラスの名前では、"CDao"というプレフィックスが付いています。 DAO クラスで ODBC データ ソースにアクセスできます。 一般に、DAO に基づいて MFC クラスは ODBC; に基づいて MFC クラスよりもより高機能ですDAO ベースのクラスは、独自のデータベース エンジンを使用して、ODBC ドライバーを含むデータにアクセスできます。 DAO ベースのクラスには、DAO を直接呼び出すことがなく、クラスを使用してテーブルの追加などのデータ定義言語 (DDL) 操作もサポートします。 ODBC クラスによってスローされた例外については、次を参照してください。 [CDBException](../../mfc/reference/cdbexception-class.md)します。  
  
 スコープ内での例外オブジェクトにアクセスすることができます、[キャッチ](../../mfc/reference/exception-processing.md#catch)式です。 スローも`CDaoException`をコードからのオブジェクト、 [AfxThrowDaoException](../../mfc/reference/exception-processing.md#afxthrowdaoexception)グローバル関数。  
  
 MFC では、DAO のすべてのエラーが型の例外として表される`CDaoException`です。 この種の例外をキャッチしたときに行うこともできます`CDaoException`データベース エンジンのエラーのコレクションに格納されている DAO エラー オブジェクトから情報を取得するメンバー関数。 各エラーが発生すると、1 つまたは複数のエラー オブジェクトがエラー コレクションに格納されます。 (通常、コレクションには、1 つのエラー オブジェクトが含まれています。、複数のエラー オブジェクトを取得する可能性が高くなりますが、ODBC データ ソースを使用している場合)。DAO の別の操作では、エラーを生成するとき、エラーのコレクションをクリアし、エラー コレクションに新しいエラー オブジェクトを配置します。 エラーを生成しない DAO 操作には、エラーのコレクションに影響を与えるありません。  
  
 DAO エラーコード DAOERR ファイルを参照してください。H. 関連情報については、「トラップ可能なデータ アクセス エラー」DAO ヘルプのトピックを参照してください。  
  
 [全般]、またはについての例外処理の詳細については`CDaoException`の資料を参照するオブジェクト、[例外処理 (MFC)](../../mfc/exception-handling-in-mfc.md)と[例外: データベースの例外](../../mfc/exceptions-database-exceptions.md)します。 2 番目の記事には、DAO での例外処理を示すサンプル コードが含まれています。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 `CDaoException`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxdao.h  
  
##  <a name="a-namecdaoexceptiona--cdaoexceptioncdaoexception"></a><a name="cdaoexception"></a>CDaoException::CDaoException  
 `CDaoException` オブジェクトを構築します。  
  
```  
CDaoException();
```  
  
### <a name="remarks"></a>コメント  
 通常は、フレームワークは、そのコードが例外をスローする場合、例外オブジェクトを作成します。 ほとんどの例外オブジェクトを明示的に作成する必要があります。 スローする場合、`CDaoException`独自のコードからグローバル関数を呼び出し[AfxThrowDaoException](../../mfc/reference/exception-processing.md#afxthrowdaoexception)します。  
  
 ただし、MFC クラスをカプセル化する DAO インターフェイス ポインターを使用して DAO の直接呼び出しを行う場合に、例外オブジェクトを明示的に作成することができます。 その場合は、DAO からエラー情報を取得する必要があります。 ワークスペースのデータベース コレクションに DAODatabases インターフェイスを使用して、DAO メソッドを呼び出すと、DAO でのエラーが発生したとします。  
  
##### <a name="to-retrieve-the-dao-error-information"></a>DAO エラー情報を取得するには  
  
1.  `CDaoException` オブジェクトを構築します。  
  
2.  例外オブジェクトの[GetErrorCount](#geterrorcount)は、データベース エンジンのエラーのコレクション内のエラー オブジェクトの数を調べます。 (通常&1; つだけ、ODBC データ ソースを使用する場合を除きます)。  
  
3.  例外オブジェクトの[GetErrorInfo](#geterrorinfo)例外オブジェクトを使用して、コレクションのインデックスでは一度に&1; つの特定のエラー オブジェクトを取得します。 例外オブジェクトは&1; つの DAO エラー オブジェクト用にプロキシと考えます。  
  
4.  現在を調べる[CDaoErrorInfo](../../mfc/reference/cdaoerrorinfo-structure.md)構造体`GetErrorInfo`で返す、 [m_pErrorInfo](#m_perrorinfo)データ メンバーです。 そのメンバーは、DAO エラーに関する情報を提供します。  
  
5.  ODBC データ ソースの場合は、手順 3. と 4. より多くのエラー オブジェクトは、必要に応じてを繰り返します。  
  
6.  ヒープ上の例外オブジェクトを構築する場合は削除して、**削除**演算子が完了したときにします。  
  
 MFC DAO クラスでのエラー処理の詳細については、記事を参照してください。[例外: データベースの例外](../../mfc/exceptions-database-exceptions.md)します。  
  
##  <a name="a-namegeterrorcounta--cdaoexceptiongeterrorcount"></a><a name="geterrorcount"></a>あります。  
 DAO データベース エンジンのエラーのコレクションのオブジェクトのエラーの数を取得するには、このメンバー関数を呼び出します。  
  
```  
short GetErrorCount();
```  
  
### <a name="return-value"></a>戻り値  
 DAO データベース エンジンのエラーのコレクションのオブジェクトのエラーの数。  
  
### <a name="remarks"></a>コメント  
 この情報はそれぞれ、コレクション内の&1; つまたは複数 DAO エラー オブジェクトを取得するエラーのコレクションをループ処理するのに便利です。 インデックス、または DAO のエラー番号によってエラー オブジェクトを取得する、 [GetErrorInfo](#geterrorinfo)メンバー関数。  
  
> [!NOTE]
>  通常のエラー コレクションには&1; つのエラー オブジェクトが存在します。 ODBC データ ソースで作業している場合、考えられます&1; つ以上。  
  
##  <a name="a-namegeterrorinfoa--cdaoexceptiongeterrorinfo"></a><a name="geterrorinfo"></a>CDaoException::GetErrorInfo  
 エラーのコレクション内には、特定のエラー オブジェクトに関するエラー情報を返します。  
  
```  
void GetErrorInfo(int nIndex);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 インデックスで検索する場合、データベース エンジンのエラーのコレクションにエラー情報のインデックス。  
  
### <a name="remarks"></a>コメント  
 次のような例外に関する情報を取得するには、このメンバー関数を呼び出します。  
  
-   エラー コード  
  
-   ソース  
  
-   説明  
  
-   ヘルプ ファイル  
  
-   ヘルプ コンテキスト  
  
 `GetErrorInfo`例外オブジェクトの情報を格納`m_pErrorInfo`データ メンバーです。 返される情報の簡単な説明を参照してください。 [m_pErrorInfo](#m_perrorinfo)します。 型の例外をキャッチした場合は`CDaoException`、MFC によってスローされた、`m_pErrorInfo`は、メンバーが既に入力されています。 DAO を直接呼び出すことを選択した場合は、例外オブジェクトを呼び出す必要があります`GetErrorInfo`メンバー関数を`m_pErrorInfo`します。 詳細な説明を参照してください、 [CDaoErrorInfo](../../mfc/reference/cdaoerrorinfo-structure.md)構造体。  
  
 DAO 例外とコード例については、記事を参照してください。[例外: データベースの例外](../../mfc/exceptions-database-exceptions.md)します。  
  
##  <a name="a-namemnafxdaoerrora--cdaoexceptionmnafxdaoerror"></a><a name="m_nafxdaoerror"></a>CDaoException::m_nAfxDaoError  
 MFC 拡張エラー コードが含まれています。  
  
### <a name="remarks"></a>コメント  
 このコードは、MFC DAO クラスの特定のコンポーネントを下がの場合で供給されます。  
  
 指定できる値は次のとおりです。  
  
- **NO_AFX_DAO_ERROR**最新の操作は、MFC の拡張エラーになりませんでした。 ただし、操作でしたが生成 DAO または OLE から他のエラーをチェックする必要がありますので[m_pErrorInfo](#m_perrorinfo)と、場合によって[m_scode](#m_scode)します。  
  
- **AFX_DAO_ERROR_ENGINE_INITIALIZATION** MFC は、Microsoft Jet データベース エンジンを初期化できませんでした。 OLE は、初期化に失敗した可能性があります。 またはそれが解除された可能性が DAO データベース エンジン オブジェクトのインスタンスを作成することです。 通常、これらの問題には、DAO または OLE が正しくインストールがお勧めします。  
  
- **AFX_DAO_ERROR_DFX_BIND** DAO レコード フィールド エクス (チェンジ DFX) 関数の呼び出しで使用するアドレスが存在しないか無効です (アドレスがデータ バインドには使用されません)。 DFX 呼び出しに無効なアドレスを渡したまたはアドレスが無効になった DFX 操作します。  
  
- **AFX_DAO_ERROR_OBJECT_NOT_OPEN**クエリ定義または開いている状態ではない、テーブル定義オブジェクトに基づくレコード セットを開こうとしました。  
  
##  <a name="a-namemperrorinfoa--cdaoexceptionmperrorinfo"></a><a name="m_perrorinfo"></a>CDaoException::m_pErrorInfo  
 ポインターを含む、`CDaoErrorInfo`前回を呼び出すことによって取得した DAO エラーのオブジェクトに関する情報を提供する構造体[GetErrorInfo](#geterrorinfo)します。  
  
### <a name="remarks"></a>コメント  
 このオブジェクトには、次の情報が含まれています。  
  
|CDaoErrorInfo メンバー|情報|説明|  
|--------------------------|-----------------|-------------|  
|**m_lErrorCode**|エラー コード|DAO のエラー コード|  
|`m_strSource`|ソース|アプリケーション エラーの発生源をオブジェクトの名前|  
|`m_strDescription`|説明|エラーに関連付けられているわかりやすい文字列|  
|`m_strHelpFile`|ヘルプ ファイル|ユーザーが、問題に関する情報を取得できる Windows のヘルプ ファイルへのパス|  
|**m_lHelpContext**|ヘルプ コンテキスト|DAO ヘルプ ファイルのトピックのコンテキスト ID|  
  
 詳細に含まれる情報については、`CDaoErrorInfo`オブジェクトを参照してください、 [CDaoErrorInfo](../../mfc/reference/cdaoerrorinfo-structure.md)構造体。  
  
##  <a name="a-namemscodea--cdaoexceptionmscode"></a><a name="m_scode"></a>CDaoException::m_scode  
 型の値を含む`SCODE`エラーを説明します。  
  
### <a name="remarks"></a>コメント  
 これは、OLE コードです。 ほとんどの場合、MFC または DAO の具体的なエラー情報は、他の利用可能なため、この値を使用する必要があります頻度の低い`CDaoException`データ メンバーです。  
  
 については`SCODE`、トピックを参照して[構造体の OLE エラー コード](http://msdn.microsoft.com/library/windows/desktop/ms690088)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。 `SCODE`データ型にマップ、`HRESULT`データ型。  
  
## <a name="see-also"></a>関連項目  
 [CException クラス](../../mfc/reference/cexception-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CException クラス](../../mfc/reference/cexception-class.md)

