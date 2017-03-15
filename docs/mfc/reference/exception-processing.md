---
title: "例外の処理 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros.exceptions
dev_langs:
- C++
helpviewer_keywords:
- macros, exception handling
- DAO (Data Access Objects), exceptions
- OLE exceptions, MFC functions
- exceptions, processing
- exception macros
- termination functions, MFC
- MFC, exceptions
- exceptions, MFC throwing functions
ms.assetid: 26d4457c-8350-48f5-916e-78f919787c30
caps.latest.revision: 16
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
ms.openlocfilehash: a2ded9c49a9f6935a5b268ccbefc4678af184029
ms.lasthandoff: 02/24/2017

---
# <a name="exception-processing"></a>例外処理
プログラムの実行時に異常な状態と「例外」と呼ばれるエラーの数に発生します。 これらには、メモリ、リソース割り当てのエラー、およびファイルを検索する障害の不足が含まれます。  
  
 Microsoft Foundation Class ライブラリは、いずれかの C++ 用 ANSI 標準委員会によって提案された後に密接にモデル化例外処理パターンを使用します。 異常状態に陥る可能性があります関数を呼び出す前に、例外ハンドラーの設定を作成する必要があります。 関数には、異常な状態が発生すると、例外が発生し、例外ハンドラーに制御が渡されます。  
  
 Microsoft Foundation Class ライブラリに含まれているいくつかのマクロは、例外ハンドラーを設定します。 さまざまなその他のグローバル関数は、必要に応じて、特殊な例外をスローして、プログラムを終了に役立ちます。 これらのマクロおよびグローバル関数は、次のカテゴリに分類されます。  
  
- 例外処理マクロは、例外ハンドラーを構成します。  
  
- 関数を Exception-throwing)、特定の種類の例外を生成します。  
  
- 終了関数には、プログラムの終了が発生します。  
  
 例と詳細については、記事を参照して[例外](../../mfc/exception-handling-in-mfc.md)します。  
  
### <a name="exception-macros"></a>例外処理マクロ  
  
|||  
|-|-|  
|[実行してください。](#try)|例外の処理のコードのブロックを指定します。|  
|[CATCH](#catch)|上記からの例外をキャッチするためのコードのブロックを指定**と**ブロックします。|  
|[CATCH_ALL](#catch_all)|上記のすべての例外をキャッチするためのコードのブロックを指定**と**ブロックします。|  
|[AND_CATCH](#and_catch)|上記の種類の追加の例外をキャッチするためのコード ブロックを指定**と**ブロックします。|  
|[AND_CATCH_ALL](#and_catch_all)|他のすべての直前に追加の例外の種類をキャッチするためのコードのブロックを指定**と**ブロックします。|  
|[END_CATCH](#end_catch)|最後の終了**キャッチ**または`AND_CATCH`コード ブロックです。|  
|[END_CATCH_ALL](#end_catch_all)|最後の終了`CATCH_ALL`コード ブロックです。|  
|[スローします。](#throw)|指定した例外をスローします。|  
|[THROW_LAST](#throw_last)|次の外側のハンドラーを現在処理されている例外をスローします。|  
  
### <a name="exception-throwing-functions"></a>例外スロー関数  
  
|||  
|-|-|  
|[AfxThrowArchiveException](#afxthrowarchiveexception)|アーカイブの例外をスローします。|  
|[AfxThrowFileException](#afxthrowfileexception)|ファイルの例外をスローします。|  
|[AfxThrowMemoryException](#afxthrowmemoryexception)|メモリ不足の例外をスローします。|  
|[AfxThrowNotSupportedException](#afxthrownotsupportedexception)|サポートされていない例外をスローします。|  
|[AfxThrowResourceException](#afxthrowresourceexception)|Windows のリソースが見つからないの例外をスローします。|  
|[AfxThrowUserException](#afxthrowuserexception)|プログラムのユーザーが開始したアクションでは、例外をスローします。|  
  
 MFC では、OLE の例外を具体的には&2; つの例外スロー関数を示します。  
  
### <a name="ole-exception-functions"></a>OLE 例外関数  
  
|||  
|-|-|  
|[AfxThrowOleDispatchException](#afxthrowoledispatchexception)|OLE オートメーション関数内で例外をスローします。|  
|[AfxThrowOleException](#afxthrowoleexception)|OLE 例外をスローします。|  
  
 データベース クラスが&2; つの例外クラスを提供するデータベースの例外をサポートするために`CDBException`と`CDaoException`、および例外の種類をサポートするためにグローバル関数。  
  
### <a name="dao-exception-functions"></a>DAO 例外関数  
  
|||  
|-|-|  
|[AfxThrowDAOException](#afxthrowdaoexception)|スローする[CDaoException](../../mfc/reference/cdaoexception-class.md)独自のコードからです。|  
|[AfxThrowDBException](#afxthrowdbexception)|スローする[CDBException](../../mfc/reference/cdbexception-class.md)独自のコードからです。|  
  
 MFC には、次の終了関数が用意されています。  
  
### <a name="termination-functions"></a>終了関数  
  
|||  
|-|-|  
|[AfxAbort](#afxabort)|呼ばれる、致命的なエラー時にアプリケーションを終了するに発生します。|  
  
##  <a name="a-nametrya--try"></a><a name="try"></a>実行してください。  
 設定、**と**ブロックします。  
  
```   
TRY   
```  
  
### <a name="remarks"></a>コメント  
 A**と**ブロックが例外をスローするコードのブロックを指定します。 これらの例外は、次に**キャッチ**と`AND_CATCH`ブロックします。 再帰が許可された: 例外は、外側に渡される可能性があります**と**ブロックを無視するかを使用して、`THROW_LAST`マクロです。 終了、**と**にブロックされること、`END_CATCH`または`END_CATCH_ALL`マクロです。  
  
 詳細については、記事を参照してください。[例外](../../mfc/exception-handling-in-mfc.md)します。  
  
### <a name="example"></a>例  
 例を参照してください[キャッチ](#catch)します。  

### <a name="requirements"></a>要件
ヘッダー: afx.h

##  <a name="a-namecatcha--catch"></a><a name="catch"></a>CATCH  
 最初に、上記でスローされた例外の種類をキャッチするコードのブロックが定義されて**と**ブロックします。  
  
```   
CATCH(exception_class, exception_object_pointer_name)  
 
```  
  
### <a name="parameters"></a>パラメーター  
 *exception_class*  
 テストするため、例外の種類を指定します。 標準的な例外クラスの一覧は、クラスを参照してください。 [CException](../../mfc/reference/cexception-class.md)します。  
  
 *ことは*  
 マクロによって作成される例外オブジェクトのポインターの名前を指定します。 内の例外オブジェクトにアクセスするポインターの名前を使用する、**キャッチ**ブロックします。 この変数を宣言します。  
  
### <a name="remarks"></a>コメント  
 例外処理コードは、例外の具体的な原因に関する詳細情報を表示、該当する場合、例外オブジェクトを問い合わせることです。 呼び出す、`THROW_LAST`処理を次の外部例外フレームにシフトするマクロ。 終了、**と**にブロックされること、`END_CATCH`マクロです。  
  
 場合*exception_class*クラス`CException`、すべての例外の種類をキャッチし、します。 使用することができます、[使うため](../../mfc/reference/cobject-class.md#iskindof)例外がスローされたかを調べます。 いくつかの種類の例外をキャッチするより良い方法は、シーケンシャルを使用する`AND_CATCH`ステートメントは、それぞれ別の例外の種類にします。  
  
 例外オブジェクトへのポインターは、マクロを作成します。 自分で宣言する必要はありません。  
  
> [!NOTE]
>  **キャッチ**ブロックは中かっこで囲んで示して C++ のスコープとして定義します。 このスコープ内の変数を宣言する場合は、そのスコープ内でのみアクセスされます。 これにも当てはまります*ことは*です。  
  
 例外の詳細については、**キャッチ**マクロ、記事を参照して[例外](../../mfc/exception-handling-in-mfc.md)します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCExceptions #&26;](../../mfc/codesnippet/cpp/exception-processing_1.cpp)]  
  
##  <a name="a-namecatchalla--catchall"></a><a name="catch_all"></a>CATCH_ALL  
 上記でスローされたすべての例外の種類をキャッチするコードのブロックが定義されて**と**ブロックします。  
  
```   
CATCH_ALL(exception_object_pointer_name)   
```  
  
### <a name="parameters"></a>パラメーター  
 *ことは*  
 マクロによって作成される例外オブジェクトのポインターの名前を指定します。 内の例外オブジェクトにアクセスするポインターの名前を使用する、`CATCH_ALL`ブロックします。 この変数を宣言します。  
  
### <a name="remarks"></a>コメント  
 例外処理コードは、例外の具体的な原因に関する詳細情報を表示、該当する場合、例外オブジェクトを問い合わせることです。 呼び出す、`THROW_LAST`処理を次の外部例外フレームにシフトするマクロ。 使用する場合`CATCH_ALL`、終了、**と**にブロックされること、`END_CATCH_ALL`マクロです。  
  
> [!NOTE]
>  `CATCH_ALL`ブロックは中かっこで囲んで示して C++ のスコープとして定義します。 このスコープ内の変数を宣言する場合は、そのスコープ内でのみアクセスされます。  
  
 例外の詳細については、記事を参照してください。[例外](../../mfc/exception-handling-in-mfc.md)します。  
  
### <a name="example"></a>例  
 例を参照してください[解放](../../mfc/reference/cfile-class.md#abort)します。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afx.h  

##  <a name="a-nameandcatcha--andcatch"></a><a name="and_catch"></a>AND_CATCH  
 直前に追加の例外の種類をキャッチするためのコードのブロックが定義されて**と**ブロックします。  
  
```   
AND_CATCH(exception_class, exception_object_pointer_name)   
```  
  
### <a name="parameters"></a>パラメーター  
 *exception_class*  
 テストするため、例外の種類を指定します。 標準的な例外クラスの一覧は、クラスを参照してください。 [CException](../../mfc/reference/cexception-class.md)します。  
  
 *ことは*  
 マクロによって作成される例外オブジェクトのポインターの名前。 内の例外オブジェクトにアクセスするポインターの名前を使用する、`AND_CATCH`ブロックします。 この変数を宣言します。  
  
### <a name="remarks"></a>コメント  
 使用して、**キャッチ**1 つの例外の種類をキャッチする、`AND_CATCH`マクロをキャッチします。 終了、**と**にブロックされること、`END_CATCH`マクロです。  
  
 例外処理コードは、例外の具体的な原因に関する詳細情報を表示、該当する場合、例外オブジェクトを問い合わせることです。 呼び出す、`THROW_LAST`内のマクロ、 `AND_CATCH` shift キーを押し、次の外部例外フレームに処理をブロックします。 `AND_CATCH`上記の末尾を示す**キャッチ**または`AND_CATCH`ブロックします。  
  
> [!NOTE]
>  `AND_CATCH`ブロックは、C++ のスコープ (中かっこで囲んで示して) として定義します。 このスコープ内の変数を宣言する場合は、そのスコープ内でのみアクセス可能であることに注意してください。 これにも当てはまります、*ことは*変数です。  
  
### <a name="example"></a>例  
 例を参照してください[キャッチ](#catch)します。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afx.h  
##  <a name="a-nameandcatchalla--andcatchall"></a><a name="and_catch_all"></a>AND_CATCH_ALL  
 直前に追加の例外の種類をキャッチするためのコードのブロックが定義されて**と**ブロックします。  
  
```   
AND_CATCH_ALL(exception_object_pointer_name)  
```  
  
### <a name="parameters"></a>パラメーター  
 *ことは*  
 マクロによって作成される例外オブジェクトのポインターの名前。 内の例外オブジェクトにアクセスするポインターの名前を使用する、`AND_CATCH_ALL`ブロックします。 この変数を宣言します。  
  
### <a name="remarks"></a>コメント  
 使用して、**キャッチ**1 つの例外の種類をキャッチする、`AND_CATCH_ALL`他のすべての後続の型をキャッチします。 使用する場合`AND_CATCH_ALL`、終了、**と**にブロックされること、`END_CATCH_ALL`マクロです。  
  
 例外処理コードは、例外の具体的な原因に関する詳細情報を表示、該当する場合、例外オブジェクトを問い合わせることです。 呼び出す、`THROW_LAST`内のマクロ、 `AND_CATCH_ALL` shift キーを押し、次の外部例外フレームに処理をブロックします。 `AND_CATCH_ALL`上記の末尾を示す**キャッチ**または`AND_CATCH_ALL`ブロックします。  
  
> [!NOTE]
>  `AND_CATCH_ALL`ブロックは、C++ のスコープ (中かっこで囲んで示して) として定義します。 このスコープ内の変数を宣言する場合は、そのスコープ内でのみアクセス可能であることに注意してください。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afx.h  
  
##  <a name="a-nameendcatcha--endcatch"></a><a name="end_catch"></a>END_CATCH  
 最後の末尾を示す**キャッチ**または`AND_CATCH`ブロックします。  
  
```   
END_CATCH  
```  
  
### <a name="remarks"></a>コメント  
 詳細については、`END_CATCH`マクロ、記事を参照して[例外](../../mfc/exception-handling-in-mfc.md)します。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afx.h  
  
##  <a name="a-nameendcatchalla--endcatchall"></a><a name="end_catch_all"></a>END_CATCH_ALL  
 最後の末尾を示す`CATCH_ALL`または`AND_CATCH_ALL`ブロックします。  
  
```   
END_CATCH_ALL  
```  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afx.h  
  
##  <a name="a-namethrowa--throw-mfc"></a><a name="throw"></a>スロー (MFC)  
 指定した例外をスローします。  
  
```   
THROW(exception_object_pointer) 
```  
  
### <a name="parameters"></a>パラメーター  
 *exception_object_pointer*  
 例外オブジェクトへのポインターから派生した`CException`します。  
  
### <a name="remarks"></a>コメント  
 **スロー**割り込みプログラムの実行、対応するコントロールの引き渡し**キャッチ**でプログラムをブロックします。 提供されていない場合、**キャッチ**コントロールが、エラーを出力メッセージを終了する Microsoft Foundation Class ライブラリ モジュールに渡されをブロックします。  
  
 詳細については、記事を参照してください。[例外](../../mfc/exception-handling-in-mfc.md)します。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afx.h  
  
##  <a name="a-namethrowlasta--throwlast"></a><a name="throw_last"></a>THROW_LAST  
 例外を次にスローバック外部**キャッチ**ブロックします。  
  
```   
THROW_LAST()   
```  
  
### <a name="remarks"></a>コメント  
 このマクロでは、ローカルで作成済みの例外をスローすることができます。 キャッチした例外をスローしようとする場合、スコープ外に出ます通常され、削除されます。 `THROW_LAST`、次に、例外が正しく渡さ**キャッチ**ハンドラー。  
  
 詳細については、記事を参照してください。[例外](../../mfc/exception-handling-in-mfc.md)します。  
  
### <a name="example"></a>例  
 例を参照してください[解放](../../mfc/reference/cfile-class.md#abort)します。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afx.h  
  
##  <a name="a-nameafxthrowarchiveexceptiona--afxthrowarchiveexception"></a><a name="afxthrowarchiveexception"></a>AfxThrowArchiveException  
 アーカイブの例外をスローします。  
  
```   
void  AfxThrowArchiveException(int cause, LPCTSTR lpszArchiveName); 
```  
  
### <a name="parameters"></a>パラメーター  
 `cause`  
 例外の原因を示す整数を指定します。 使用可能な値の一覧は、次を参照してください。 [CArchiveException::m_cause](../../mfc/reference/carchiveexception-class.md#m_cause)します。  
  
 `lpszArchiveName`  
 名前を含む文字列を指す、 `CArchive` (該当する場合)、例外を発生させたオブジェクト。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afx.h  
  
##  <a name="a-nameafxthrowfileexceptiona--afxthrowfileexception"></a><a name="afxthrowfileexception"></a>AfxThrowFileException  
 ファイルの例外をスローします。  
  
```   
void AfxThrowFileException(
    int cause,  
    LONG lOsError = -1,  
    LPCTSTR lpszFileName = NULL); 
```  
  
### <a name="parameters"></a>パラメーター  
 `cause`  
 例外の原因を示す整数を指定します。 使用可能な値の一覧は、次を参照してください。[については、「](../../mfc/reference/cfileexception-class.md#m_cause)します。  
  
 `lOsError`  
 オペレーティング システム エラー番号が含まれています (該当する場合) を示す例外の原因です。 エラー コードの一覧については、オペレーティング システムのマニュアルを参照してください。  
  
 `lpszFileName`  
 (該当する場合)、例外の原因となったファイルの名前を含む文字列へのポインター。  
  
### <a name="remarks"></a>コメント  
 オペレーティング システムのエラー コードに基づいて原因の特定を担当しています。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afx.h  
  
##  <a name="a-nameafxthrowmemoryexceptiona--afxthrowmemoryexception"></a><a name="afxthrowmemoryexception"></a>AfxThrowMemoryException  
 メモリ不足の例外をスローします。  
  
```   
void AfxThrowMemoryException(); 
```  
  
### <a name="remarks"></a>コメント  
 場合に、この関数を呼び出す基になるシステム メモリ アロケーターへの呼び出し (など`malloc`と[GlobalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366574) Windows 関数) は失敗します。 呼び出す必要はありません**新しい**ため**新しい**メモリの割り当てが失敗した場合は自動的にメモリ不足例外がスローされます。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afx.h  
  
##  <a name="a-nameafxthrownotsupportedexceptiona--afxthrownotsupportedexception"></a><a name="afxthrownotsupportedexception"></a>AfxThrowNotSupportedException  
 サポートされていない機能の要求の結果である例外をスローします。  
  
```  
void AfxThrowNotSupportedException(); 
```  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afx.h  
  
##  <a name="a-nameafxthrowresourceexceptiona--afxthrowresourceexception"></a><a name="afxthrowresourceexception"></a>AfxThrowResourceException  
 リソースの例外をスローします。  
  
```   
void  AfxThrowResourceException(); 
```  
  
### <a name="remarks"></a>コメント  
 この関数は通常、Windows のリソースを読み込むことができないときに呼び出されます。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afx.h  
  
##  <a name="a-nameafxthrowuserexceptiona--afxthrowuserexception"></a><a name="afxthrowuserexception"></a>AfxThrowUserException  
 エンドユーザーの操作を停止する例外をスローします。  
  
```   
void AfxThrowUserException(); 
```  
  
### <a name="remarks"></a>コメント  
 この関数は通常、直後に呼び出される`AfxMessageBox`をユーザーにエラーが発生しています。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afx.h  
  
##  <a name="a-nameafxthrowoledispatchexceptiona--afxthrowoledispatchexception"></a><a name="afxthrowoledispatchexception"></a>AfxThrowOleDispatchException  
 OLE オートメーション関数内で例外をスローするのにには、この関数を使用します。  
  
```   
void AFXAPI AfxThrowOleDispatchException(
    WORD wCode ,  
    LPCSTR lpszDescription,  
    UINT nHelpID = 0);

void AFXAPI AfxThrowOleDispatchException(
    WORD wCode,  
    UINT nDescriptionID,  
    UINT nHelpID = -1); 
```  
  
### <a name="parameters"></a>パラメーター  
 `wCode`  
 アプリケーションに固有のエラー コード。  
  
 `lpszDescription`  
 エラーの口頭で説明します。  
  
 `nDescriptionID`  
 言葉によるエラーの説明のリソース ID です。  
  
 `nHelpID`  
 アプリケーションのヘルプのヘルプ コンテキスト (します。HLP) ファイルです。  
  
### <a name="remarks"></a>コメント  
 この関数に提供される情報は、制御するアプリケーション (Microsoft Visual Basic または別の OLE オートメーションのクライアント アプリケーション) で表示できます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCExceptions&#25;](../../mfc/codesnippet/cpp/exception-processing_2.cpp)]  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afx.h  
  
##  <a name="a-nameafxthrowoleexceptiona--afxthrowoleexception"></a><a name="afxthrowoleexception"></a>AfxThrowOleException  
 型のオブジェクトを作成する`COleException`例外をスローします。  
  
``` 
void AFXAPI AfxThrowOleException(SCODE sc);
void AFXAPI AfxThrowOleException(HRESULT hr); 
```  
  
### <a name="parameters"></a>パラメーター  
 `sc`  
 例外の原因を示す OLE ステータス コードです。  
  
 `hr`  
 例外の原因を示す結果コードへのハンドルします。  
  
### <a name="remarks"></a>コメント  
 受け取るバージョンで、`HRESULT`引数に対応する、その結果コードの変換を行う`SCODE`します。 詳細については`HRESULT`と`SCODE`を参照してください[COM エラー コードの構造体](http://msdn.microsoft.com/library/windows/desktop/ms690088)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdao.h  
  
##  <a name="a-nameafxthrowdaoexceptiona--afxthrowdaoexception"></a><a name="afxthrowdaoexception"></a>AfxThrowDaoException  
 型の例外をスローするには、この関数を呼び出す[CDaoException](../../mfc/reference/cdaoexception-class.md)独自のコードからです。  
  
```   
void AFXAPI AfxThrowDaoException(
    int nAfxDaoError = NO_AFX_DAO_ERROR,  
    SCODE scode = S_OK); 
```  
  
### <a name="parameters"></a>パラメーター  
 `nAfxDaoError`  
 DAO の拡張エラー コードを表す整数値をすることができます、値の&1; つ下に表示されます[CDaoException::m_nAfxDaoError](../../mfc/reference/cdaoexception-class.md#m_nafxdaoerror)します。  
  
 *scode*  
 型の DAO の OLE エラー コード`SCODE`します。 詳細については、次を参照してください。 [CDaoException::m_scode](../../mfc/reference/cdaoexception-class.md#m_scode)します。  
  
### <a name="remarks"></a>コメント  
 フレームワークと記述も`AfxThrowDaoException`です。 呼び出しでは、パラメーターのいずれかまたは両方を渡すことができます。 たとえばのいずれかの引き上げを希望する場合、エラーで定義されている**CDaoException::nAfxDaoError**する気にせず、 *scode*パラメーターで有効なコードを渡す、`nAfxDaoError`パラメーターの既定値をそのまま使用し、 *scode*します。  
  
 MFC DAO クラスに関連する例外については、クラスを参照してください。 `CDaoException` 」および「この本で[例外: データベースの例外](../../mfc/exceptions-database-exceptions.md)します。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdb.h  
  
##  <a name="a-nameafxthrowdbexceptiona--afxthrowdbexception"></a><a name="afxthrowdbexception"></a>AfxThrowDBException  
 型の例外をスローするには、この関数を呼び出す`CDBException`独自のコードからです。  
  
```  
void AfxThrowDBException(
    RETCODE nRetCode,  
    CDatabase* pdb,  
    HSTMT hstmt);  
```  
  
### <a name="parameters"></a>パラメーター  
 `nRetCode`  
 型の値**へ**例外がスローされる原因となったエラーの種類を定義します。  
  
 `pdb`  
 ポインター、`CDatabase`例外が関連付けられているデータ ソース接続を表すオブジェクト。  
  
 `hstmt`  
 ODBC **HSTMT**例外が関連付けられているステートメント ハンドルを指定するハンドル。  
  
### <a name="remarks"></a>コメント  
 Framework 呼び出し`AfxThrowDBException`受信すると、ODBC**へ**ODBC API の呼び出しをからに機能し、解釈、**へ**expectable エラーではなく、例外的な状態として。 などのデータ アクセス操作は、ディスクの読み取りエラーのため失敗します。  
  
 については、**へ**、ODBC で定義されている値の第 8 章「を取得するステータスおよびエラーについては、」を参照してください、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。 これらのコードに MFC の拡張機能の概要については、クラスを参照してください。 [CDBException](../../mfc/reference/cdbexception-class.md)します。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afx.h  
  
##  <a name="a-nameafxaborta--afxabort"></a><a name="afxabort"></a>AfxAbort  
 MFC によって提供される既定の終了関数です。  
  
```   
void  AfxAbort(); 
```  
  
### <a name="remarks"></a>コメント  
 `AfxAbort`内部的に呼び出されます MFC メンバー関数によって処理できないキャッチされない例外などの致命的なエラーがある場合。 呼び出すことができます`AfxAbort`回復できない致命的なエラーが発生した場合は、まれなケースです。  
  
### <a name="example"></a>例  
 例を参照してください[キャッチ](#catch)します。  

### <a name="requirements"></a>要件  
  **ヘッダー** afx.h   
  
## <a name="see-also"></a>関連項目  
 [マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)   
 [CException クラス](../../mfc/reference/cexception-class.md)

