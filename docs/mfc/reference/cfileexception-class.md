---
title: "未定義のままクラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CFileException
- AFX/CFileException
- AFX/CFileException::CFileException
- AFX/CFileException::ErrnoToException
- AFX/CFileException::GetErrorMessage
- AFX/CFileException::OsErrorToException
- AFX/CFileException::ThrowErrno
- AFX/CFileException::ThrowOsError
- AFX/CFileException::m_cause
- AFX/CFileException::m_lOsError
- AFX/CFileException::m_strFileName
dev_langs:
- C++
helpviewer_keywords:
- CFile class, exceptions of
- exceptions, file type
- CFileException class
ms.assetid: f6491bb9-bfbc-42fd-a952-b33f9b62323f
caps.latest.revision: 20
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: d9064ae66f0dcd0e9f0dce0eedd8e38353f9da06
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="cfileexception-class"></a>未定義のままクラス
ファイルに関連した例外状態を表します。  
  
## <a name="syntax"></a>構文  
  
```  
class CFileException : public CException  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CFileException::CFileException](#cfileexception)|`CFileException` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CFileException::ErrnoToException](#errnotoexception)|原因、実行時のエラー番号に対応するコードを返します。|  
|[CFileException::GetErrorMessage](#geterrormessage)|例外を説明するメッセージを取得します。|  
|[CFileException::OsErrorToException](#oserrortoexception)|オペレーティング システム エラー コードに対応する原因のコードを返します。|  
|[CFileException::ThrowErrno](#throwerrno)|ランタイム エラー番号に基づくファイルの例外をスローします。|  
|[CFileException::ThrowOsError](#throwoserror)|オペレーティング システム エラー番号に基づくファイルの例外をスローします。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[については、「](#m_cause)|例外の原因に対応する移植可能なコードが含まれています。|  
|[CFileException::m_lOsError](#m_loserror)|関連するオペレーティング システム エラー番号が含まれています。|  
|[CFileException::m_strFileName](#m_strfilename)|この例外のファイルの名前が含まれています。|  
  
## <a name="remarks"></a>コメント  
 `CFileException`クラスには、ポータブル原因コードとオペレーティング システム固有のエラー番号を保持するパブリック データ メンバーが含まれています。 クラスは、ファイルの例外をスローして、オペレーティング システム エラーと C ランタイム エラーの両方の原因コードを返すためにも静的メンバー関数を提供します。  
  
 `CFileException`オブジェクトが構築されでスローされた`CFile`メンバー関数と派生クラスのメンバー関数。 これらのオブジェクトのスコープ内にアクセスすることができます、**キャッチ**式です。 移植性を原因コードのみを使用して、例外の理由を取得します。 例外の詳細については、記事を参照してください。[例外処理 (MFC)](../../mfc/exception-handling-in-mfc.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 `CFileException`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afx.h  
  
##  <a name="cfileexception"></a>CFileException::CFileException  
 構築、`CFileException`原因コードとオペレーティング システムのコードをオブジェクトに格納するオブジェクト。  
  
```  
CFileException(
    int cause = CFileException::none,  
    LONG lOsError = -1,  
    LPCTSTR lpszArchiveName = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `cause`  
 例外の原因を示す列挙型の変数。 参照してください[については、「](#m_cause)の有効な値の一覧です。  
  
 `lOsError`  
 使用可能な場合は、例外のオペレーティング システム固有理由です。 `lOsError`パラメーターより多くの情報を提供`cause`です。  
  
 `lpszArchiveName`  
 名前を含む文字列を指す、`CFile`オブジェクトの例外が発生します。  
  
### <a name="remarks"></a>コメント  
 このコンス トラクターを直接使用されませんではなく、グローバル関数を呼び出す[AfxThrowFileException](exception-processing.md#afxthrowfileexception)します。  
  
> [!NOTE]
>  変数`lOsError`にのみ適用されます`CFile`と`CStdioFile`オブジェクトです。 `CMemFile`クラスは、このエラー コードを処理しません。  
  
##  <a name="errnotoexception"></a>CFileException::ErrnoToException  
 特定のランタイム ライブラリのエラー値に変換、`CFileException`エラー値を列挙します。  
  
```  
static int PASCAL ErrnoToException(int nErrno);
```  
  
### <a name="parameters"></a>パラメーター  
 `nErrno`  
 整数エラー コード、実行時のインクルード ファイル ERRNO で定義されています。H.  
  
### <a name="return-value"></a>戻り値  
 特定のランタイム ライブラリのエラー値に対応する列挙値。  
  
### <a name="remarks"></a>コメント  
 参照してください[については、「](#m_cause) 、候補のリストの列挙値。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCFiles #&26;](../../atl-mfc-shared/reference/codesnippet/cpp/cfileexception-class_1.cpp)]  
  
##  <a name="geterrormessage"></a>CFileException::GetErrorMessage  
 例外を説明するテキストを取得します。  
  
```  
virtual BOOL GetErrorMessage(
    LPTSTR lpszError,  
    UINT nMaxError,  
    PUINT pnHelpContext = NULL) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力、出力] `lpszError`  
 エラー メッセージを受信するバッファーへのポインター。  
  
 [入力] `nMaxError`  
 指定したバッファーに保持できる文字の最大数。 これには、終端の null 文字が含まれます。  
  
 [入力、出力] `pnHelpContext`  
 ヘルプ コンテキスト ID を受信する符号なし整数へのポインター 場合`NULL`ID は返されません。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`メソッドが成功した場合それ以外の場合`FALSE`します。  
  
### <a name="remarks"></a>コメント  
 指定されたバッファーが小さすぎる場合は、エラー メッセージが切り捨てられます。  
  
### <a name="example"></a>例  
 次の例では使用`CFileException::GetErrorMessage`します。  
  
 [!code-cpp[NVC_MFCExceptions #&22;](../../mfc/codesnippet/cpp/cfileexception-class_2.cpp)]  
  
##  <a name="m_cause"></a>については、「  
 `CFileException` 列挙型によって定義された値が含まれます。  
  
```  
int m_cause;  
```  
  
### <a name="remarks"></a>コメント  
 このデータ メンバーは `int` 型のパブリック変数です。 列挙子とその意味は次のとおりです。  
  
- `CFileException::none`0: エラーが発生していません。  
  
- `CFileException::genericException`1: 未指定のエラーが発生しました。  
  
- `CFileException::fileNotFound`2: ファイルが見つかりませんでした。  
  
- `CFileException::badPath`3: パスの一部またはすべてが無効です。  
  
- `CFileException::tooManyOpenFiles`4: 開いているファイルのアクセス許可の数を超えています。  
  
- `CFileException::accessDenied`5: ファイルにアクセスできませんでした。  
  
- `CFileException::invalidFile`6: 無効なファイル ハンドルを使用する試みが発生しました。  
  
- `CFileException::removeCurrentDir`7: 現在の作業ディレクトリを削除することはできません。  
  
- `CFileException::directoryFull`8: ディレクトリのエントリがありません。  
  
- `CFileException::badSeek`9: ファイル ポインターを設定しようとしてエラーが発生しました。  
  
- `CFileException::hardIO`10: ハードウェア エラーが発生しました。  
  
- `CFileException::sharingViolation`11: 共有します。Exe ファイルが読み込まれていないか、共有領域がロックされました。  
  
- `CFileException::lockViolation`12: 既にロックされている領域をロックしようとしましたがあります。  
  
- `CFileException::diskFull`14: ディスクがいっぱいです。  
  
- `CFileException::endOfFile`15: ファイルの末尾に達しました。  
  
    > [!NOTE]
    >  これらの `CFileException` 原因列挙子は、`CArchiveException` 原因列挙子とは異なります。  
  
    > [!NOTE]
    > `CArchiveException::generic` は使用されなくなりました。 代わりに、`genericException` を使用してください。 `generic` をアプリケーションで使用して /clr でビルドした場合、発生した構文エラーを解読するのは困難です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCFiles #&30;](../../atl-mfc-shared/reference/codesnippet/cpp/cfileexception-class_3.cpp)]  
  
##  <a name="m_loserror"></a>CFileException::m_lOsError  
 この例外のオペレーティング システムのエラー コードが含まれています。  
  
```  
LONG m_lOsError;  
```  
  
### <a name="remarks"></a>コメント  
 エラー コードの一覧については、オペレーティング システム技術マニュアルを参照してください。 このデータ メンバーは型のパブリック変数**長い**します。  
  
##  <a name="m_strfilename"></a>CFileException::m_strFileName  
 この例外の状態のファイルの名前が含まれています。  
  
```  
CString m_strFileName;  
```  
  
##  <a name="oserrortoexception"></a>CFileException::OsErrorToException  
 対応する列挙子を返します、指定された`lOsError`値。 エラー コードは不明でかどうかは、この関数を返します**定義**します。  
  
```  
static int PASCAL OsErrorToException(LONG lOsError);
```  
  
### <a name="parameters"></a>パラメーター  
 `lOsError`  
 オペレーティング システム固有のエラー コード。  
  
### <a name="return-value"></a>戻り値  
 指定したオペレーティング システムのエラー値に対応する列挙値。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCFiles #&27;](../../atl-mfc-shared/reference/codesnippet/cpp/cfileexception-class_4.cpp)]  
  
##  <a name="throwerrno"></a>CFileException::ThrowErrno  
 構築、`CFileException`オブジェクトに対応する、指定された`nErrno`し、例外をスローします。  
  
```  
static void PASCAL ThrowErrno(int nErrno, LPCTSTR lpszFileName = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `nErrno`  
 整数エラー コード、実行時のインクルード ファイル ERRNO で定義されています。H.  
  
 `lpszFileName`  
 ファイルの名前を含む文字列へのポインターの原因となった例外、利用可能な場合です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCFiles #&28;](../../atl-mfc-shared/reference/codesnippet/cpp/cfileexception-class_5.cpp)]  
  
##  <a name="throwoserror"></a>CFileException::ThrowOsError  
 スロー、`CFileException`に対応する、指定された`lOsError`値。 エラー コードが不明、し、関数としてコード化された例外をスローするかどうかは**定義**します。  
  
```  
static void PASCAL ThrowOsError(LONG lOsError, LPCTSTR lpszFileName = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `lOsError`  
 オペレーティング システム固有のエラー コード。  
  
 `lpszFileName`  
 ファイルの名前を含む文字列へのポインターの原因となった例外、利用可能な場合です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCFiles #&29;](../../atl-mfc-shared/reference/codesnippet/cpp/cfileexception-class_6.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [CException クラス](../../mfc/reference/cexception-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [例外の処理](../../mfc/reference/exception-processing.md)




