---
title: "CException クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CException
- AFX/CException
- AFX/CException::CException
- AFX/CException::Delete
- AFX/CException::ReportError
dev_langs:
- C++
helpviewer_keywords:
- COleDispatchException class, base class
- CException class
- exceptions, classes for
- CInternetException class, base class
- macros, exception handling
- CNotSupportedException class, base class
- CFileException class, base class
- CDBException class, base class
- CArchiveException class, base class
- CUserException class
- CDaoException class, base class
- CMemoryException class, base class
- COleException class, base class
- CResourceException class, base class
ms.assetid: cfacf14d-bfe4-4666-a5c7-38b800512920
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 4cbb69ff79a1b201260d83b1bd568b63519a33b5
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="cexception-class"></a>CException クラス
MFC (Microsoft Foundation Class) ライブラリ内のすべての例外に関する基底クラスです。  
  
## <a name="syntax"></a>構文  
  
```  
class AFX_NOVTABLE CException : public CObject  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CException::CException](#cexception)|`CException` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CException::Delete](#delete)|削除、`CException`オブジェクトです。|  
|[CException::ReportError](#reporterror)|ユーザーにメッセージ ボックスに、エラー メッセージを報告します。|  
  
## <a name="remarks"></a>コメント  
 `CException`抽象基本クラスを作成することはできませんが、`CException`オブジェクト直接派生クラスのオブジェクトを作成する必要があります。 独自に作成する必要がある場合`CException`のスタイル クラスは、派生クラスをモデルとして上記のいずれかを使用します。 派生クラスにも使用`IMPLEMENT_DYNAMIC`します。  
  
 派生クラスとその説明を次に示します。  
  
|||  
|-|-|  
|[CSimpleException](../../mfc/reference/csimpleexception-class.md)|リソース クリティカルな MFC 例外の基本クラス|  
|[CInvalidArgException](../../mfc/reference/cinvalidargexception-class.md)|無効な引数の例外状態|  
|[関数](../../mfc/reference/cmemoryexception-class.md)|メモリ不足の例外|  
|[行わない](../../mfc/reference/cnotsupportedexception-class.md)|サポートされていない操作の要求|  
|[CArchiveException](../../mfc/reference/carchiveexception-class.md)|アーカイブ固有の例外|  
|[未定義のまま](../../mfc/reference/cfileexception-class.md)|特定のファイルの例外|  
|[関数](../../mfc/reference/cresourceexception-class.md)|Windows リソース見つからないか、または不可能|  
|[関数](../../mfc/reference/coleexception-class.md)|OLE 例外|  
|[CDBException](../../mfc/reference/cdbexception-class.md)|データベースの例外 (つまり、Open Database Connectivity に基づいて MFC データベース クラス用により発生する例外条件)|  
|[メンバー](../../mfc/reference/coledispatchexception-class.md)|OLE ディスパッチ (オートメーション) 例外|  
|[チェック](../../mfc/reference/cuserexception-class.md)|リソースが検出できなかったことを示す例外|  
|[CDaoException](../../mfc/reference/cdaoexception-class.md)|データ アクセス オブジェクトの例外 (つまり、DAO クラスに発生する例外条件)|  
|[表す](../../mfc/reference/cinternetexception-class.md)|インターネットの例外 (つまり、インターネット クラスの発生する例外条件)。|  
  
 使用するためのものではこれらの例外、[スロー](exception-processing.md#throw)、 [THROW_LAST](exception-processing.md#throw_last)、[ください](exception-processing.md#try)、[キャッチ](exception-processing.md#catch)、 [and_catch](exception-processing.md#and_catch)と[end_catch](exception-processing.md#end_catch)マクロです。 例外の詳細については、次を参照してください。[例外の処理](exception-processing.md)、」または「[例外処理 (MFC)](../exception-handling-in-mfc.md)します。  
  
 特定の例外をキャッチするには、適切な派生クラスを使用します。 すべての種類の例外を使用して`CException`をクリックして[使うため](cobject-class.md#iskindof)を区別する`CException`-派生クラスです。 注意`CObject::IsKindOf`では、クラスに対してのみが宣言された、 [IMPLEMENT_DYNAMIC](run-time-object-model-services.md#implement_dynamic)マクロは、動的な型チェックを活用するためにします。 任意`CException`-作成した派生クラスを使用する必要があります、`IMPLEMENT_DYNAMIC`マクロ、すぎます。  
  
 呼び出して、ユーザーに例外に関する詳細をレポートできます[GetErrorMessage](cfileexception-class.md#geterrormessage)または[ReportError](#reporterror)、2 つのメンバー関数のいずれかで使用できる`CException`のクラスを派生します。  
  
 マクロのいずれかによって、例外がキャッチされた場合、`CException`オブジェクトが自動的に削除されます。 削除しないでください、自分でします。 使用して、例外がキャッチされた場合、**キャッチ**キーワードは自動的に削除されません。 記事を参照して[例外処理 (MFC)](../exception-handling-in-mfc.md)詳細については、例外オブジェクトを削除する場合。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](cobject-class.md)  
  
 `CException`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afx.h  
  
##  <a name="cexception"></a>CException::CException  
 このメンバー関数を作成、`CException`オブジェクトです。  
  
```  
explicit CException(BOOL bAutoDelete);
```  
  
### <a name="parameters"></a>パラメーター  
 *b_AutoDelete*  
 指定**TRUE**場合のメモリを`CException`オブジェクトがヒープに割り当てられています。 これにより、`CException`ときに削除するオブジェクト、**削除**例外を削除するメンバー関数が呼び出されます。 指定**FALSE**場合、`CException`オブジェクトがスタック上またはグローバル オブジェクトです。 ここで、`CException`オブジェクトはできない時に削除、**削除**メンバー関数が呼び出されます。  
  
### <a name="remarks"></a>コメント  
 このコンス トラクターを直接呼び出す必要は通常ことはありません。 例外をスローする関数のインスタンスを作成する必要があります、 `CException`-クラスを派生し、呼び出すコンス トラクター、またはそれが、MFC のいずれかの使用をスローする関数など[AfxThrowFileException](exception-processing.md#afxthrowfileexception)、定義済みの型をスローします。 このドキュメントは完全を期すのためだけに提供します。  
  
##  <a name="delete"></a>CException::Delete  
 この関数はかどうかをチェック、 **CException** 、ヒープのオブジェクトを作成したし、場合は、**削除**演算子をオブジェクトにします。  
  
```  
void Delete();
```  
  
### <a name="remarks"></a>コメント  
 削除するときに、 **CException**オブジェクトを使用、**削除**例外を削除するメンバー関数。 使用しないでください、**削除**演算子を直接ため、`CException`オブジェクト グローバル オブジェクトがあります。 または、スタック上に作成します。  
  
 オブジェクトを作成するときに、オブジェクトを削除するかどうかを指定することができます。 詳細については、次を参照してください。 [CException::CException](#cexception)します。  
  
 のみを呼び出す必要がある**削除**、C++ を使用している場合**しようと**- **キャッチ**メカニズムです。 MFC のマクロを使用している場合**しようと**と**キャッチ**、これらのマクロはこの関数を呼び出すは自動的にします。  
  
### <a name="example"></a>例  
 ```cpp  
 CFile* pFile = NULL;
// Constructing a CFile object with this override may throw
// a CFile exception, and won't throw any other exceptions.
// Calling CString::Format() may throw a CMemoryException,
// so we have a catch block for such exceptions, too. Any
// other exception types this function throws will be
// routed to the calling function.
// Note that this example performs the same actions as the 
// example for CATCH, but uses C++ try/catch syntax instead
// of using the MFC TRY/CATCH macros. This sample must use
// CException::Delete() to delete the exception objects
// before closing the catch block, while the CATCH example
// implicitly performs the deletion via the macros.
try
{
   pFile = new CFile(_T("C:\\WINDOWS\\SYSTEM.INI"),
      CFile::modeRead | CFile::shareDenyNone);
   ULONGLONG ullLength = pFile->GetLength();
   CString str;
   str.Format(_T("Your SYSTEM.INI file is %u bytes long."), ullLength);
   AfxMessageBox(str);
}
catch(CFileException* pEx)
{
   // Simply show an error message to the user.
   pEx->ReportError();
   pEx->Delete();
}
catch(CMemoryException* pEx)
{
   // We can't recover from this memory exception, so we'll
   // just terminate the app without any cleanup. Normally, an
   // an application should do everything it possibly can to
   // clean up properly and _not_ call AfxAbort().
   pEx->Delete();
   AfxAbort();
}
// If an exception occurrs in the CFile constructor,
// the language will free the memory allocated by new
// and will not complete the assignment to pFile.
// Thus, our clean-up code needs to test for NULL.
if (pFile != NULL)
{
   pFile->Close();
   delete pFile;
}   
 ```
  
##  <a name="reporterror"></a>CException::ReportError  
 ユーザーにメッセージ ボックスにエラー テキストをレポートするには、このメンバー関数を呼び出します。  
  
```  
virtual int ReportError(
    UINT nType = MB_OK,  
    UINT nMessageID = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 `nType`  
 メッセージ ボックスのスタイルを指定します。 任意の組み合わせを適用、[メッセージ ボックス スタイル](message-box-styles.md)します。 このパラメーターを指定しない場合、既定値は**MB_OK**します。  
  
 *nMessageID*  
 例外オブジェクトには、エラー メッセージがない場合に表示するメッセージのリソース ID (ストリング テーブル エントリ) を指定します。 0 の場合、メッセージ"エラー メッセージはありません"が表示されます。  
  
### <a name="return-value"></a>戻り値  
 `AfxMessageBox`値、メッセージ ボックスを表示するための十分なメモリがそれ以外の場合は 0 です。 参照してください[AfxMessageBox](cstring-formatting-and-message-box-display.md#afxmessagebox)戻り値にします。  
  
### <a name="example"></a>例  
 使用例を次に示します`CException::ReportError`します。 別の例の例を参照してください。[キャッチ](exception-processing.md#catch)します。  
  
```cpp  
CFile fileInput;
CFileException ex;

// try to open a file for reading.  
// The file will certainly not
// exist because there are too many explicit
// directories in the name.

// if the call to Open() fails, ex will be
// initialized with exception
// information.  the call to ex.ReportError() will
// display an appropriate
// error message to the user, such as
// "\Too\Many\Bad\Dirs.DAT contains an
// invalid path."  The error message text will be
// appropriate for the
// file name and error condition.

if (!fileInput.Open(_T("\\Too\\Many\\Bad\\Dirs.DAT"), CFile::modeRead, &ex))
{
  ex.ReportError();
}
else
{
  // the file was opened, so do whatever work
  // with fileInput we were planning...

  fileInput.Close();
}
```

## <a name="see-also"></a>関連項目  
 [CObject クラス](cobject-class.md)   
 [階層図](../hierarchy-chart.md)   
 [例外の処理](exception-processing.md)   
 [方法: 独自のカスタム例外クラスを作成します。](http://go.microsoft.com/fwlink/linkid=128045)



