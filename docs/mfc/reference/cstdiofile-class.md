---
title: "CStdioFile クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CStdioFile
dev_langs:
- C++
helpviewer_keywords:
- CStdioFile class
- I/O [MFC], stream
- stream I/O
ms.assetid: 88c2274c-4f0e-4327-882a-557ba4b3ae15
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
ms.openlocfilehash: f3f036b409067676fdf12db9751cac1ea8025140
ms.lasthandoff: 02/24/2017

---
# <a name="cstdiofile-class"></a>CStdioFile クラス
ランタイム関数で開かれた C ランタイム ストリーム ファイルを表す[fopen](../../c-runtime-library/reference/fopen-wfopen.md)します。  
  
## <a name="syntax"></a>構文  
  
```  
class CStdioFile : public CFile  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CStdioFile::CStdioFile](#cstdiofile)|構築、`CStdioFile`パスまたはファイルのポインターからのオブジェクト。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CStdioFile::Open](#open)|オーバーロードされます。 開くが、既定で使用するために設計された`CStdioFile`コンス トラクター (オーバーライド[CFile::Open](../../mfc/reference/cfile-class.md#open))。|  
|[CStdioFile::ReadString](#readstring)|単一行のテキストを読み取ります。|  
|[CStdioFile::Seek](#seek)|現在のファイル ポインターを移動します。|  
|[CStdioFile::WriteString](#writestring)|単一行のテキストを書き込みます。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CStdioFile::m_pStream](#m_pstream)|開いているファイルへのポインターが含まれています。|  
  
## <a name="remarks"></a>コメント  
 ストリームのファイルは、バッファーに格納され、テキスト モード (既定値) またはバイナリ モードのいずれかで開くことができます。  
  
 テキスト モードでは、キャリッジ リターンとライン フィードのペアの特殊な処理を提供します。 改行文字を記述する文字 (0x0A) テキスト モードを`CStdioFile`オブジェクトのバイトのペア (0x0D、0x0A) ファイルに送信します。 読み込んだとき、バイトのペア (0x0D、0x0A) は、1 バイトの 0x0A に変換します。  
  
 [CFile](../../mfc/reference/cfile-class.md)関数[複製](../../mfc/reference/cfile-class.md#duplicate)、 [LockRange](../../mfc/reference/cfile-class.md#lockrange)、および[UnlockRange](../../mfc/reference/cfile-class.md#unlockrange)はサポートされていません`CStdioFile`します。  
  
 これらの関数を呼び出した場合、 `CStdioFile`、表示される、[行わない](../../mfc/reference/cnotsupportedexception-class.md)します。  
  
 使用する方法について`CStdioFile`、記事を参照して[MFC のファイル](../../mfc/files-in-mfc.md)と[ファイル処理](../../c-runtime-library/file-handling.md)で、*ランタイム ライブラリ リファレンス*します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 `CStdioFile`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afx.h  
  
##  <a name="a-namecstdiofilea--cstdiofilecstdiofile"></a><a name="cstdiofile"></a>CStdioFile::CStdioFile  
 `CStdioFile` オブジェクトを構築して初期化します。  
  
```  
CStdioFile();  
CStdioFile(CAtlTransactionManager* pTM);  
  CStdioFile(FILE* pOpenStream);

 
CStdioFile(
    LPCTSTR lpszFileName,  
    UINT nOpenFlags);

 
CStdioFile(
    LPCTSTR lpszFileName,
    UINT nOpenFlags,
    CAtlTransactionManager* pTM);
```  
  
### <a name="parameters"></a>パラメーター  
 `pOpenStream`  
 C ランタイム関数への呼び出しによって返されたファイル ポインターを指定[fopen](../../c-runtime-library/reference/fopen-wfopen.md)します。  
  
 `lpszFileName`  
 目的のファイルへのパスを表す文字列を指定します。 相対パスまたは絶対パスができます。  
  
 `nOpenFlags`  
 ファイルの作成、ファイルの共有、およびファイル アクセス モードのオプションを指定します。 ビットごとの OR を使用して複数のオプションを指定することができます ( `|`) 演算子。  
  
 1 つのファイル アクセス モード オプションが必要です。その他のモードはオプションです。 参照してください[ほか](../../mfc/reference/cfile-class.md#cfile)モードのオプションとその他のフラグの一覧にします。 Mfc バージョン 3.0 以降では、共有フラグを使用します。  
  
 `pTM`  
 CAtlTransactionManager オブジェクトへのポインター。  
  
### <a name="remarks"></a>コメント  
 既定のコンス トラクターがファイルを添付できません、`CStdioFile`オブジェクトです。 このコンス トラクターを使用する場合は、使用、`CStdioFile::Open`ファイルを開きにアタッチする方法、`CStdioFile`オブジェクトです。  
  
 単一パラメーター コンス トラクターは、アタッチ、開いているファイル ストリームを`CStdioFile`オブジェクトです。 定義済みの入力/出力ファイル ポインターのポインター値が許可される`stdin`、 `stdout`、または`stderr`です。  
  
 2 つのパラメーターのコンス トラクターを作成、`CStdioFile`オブジェクトし、指定されたパスに対応するファイルを開きます。  
  
 渡した場合`NULL`のいずれか`pOpenStream`または`lpszFileName`、コンス トラクターは、スロー、`CInvalidArgException*`です。  
  
 コンス トラクターがスローした場合は、ファイルを開けないか、作成、`CFileException*`です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCFiles #&37;](../../atl-mfc-shared/reference/codesnippet/cpp/cstdiofile-class_1.cpp)]  
  
##  <a name="a-namempstreama--cstdiofilempstream"></a><a name="m_pstream"></a>CStdioFile::m_pStream  
 `m_pStream`データ メンバーは、C ランタイム関数によって返される、開いているファイルへのポインターを`fopen`です。  
  
```  
FILE* m_pStream;  
```  
  
### <a name="remarks"></a>コメント  
 **NULL**ファイルが開かれていなかったまたはが閉じられました。  
  
##  <a name="a-nameopena--cstdiofileopen"></a><a name="open"></a>CStdioFile::Open  
 オーバーロードされます。 開くが、既定で使用するために設計された`CStdioFile`コンス トラクターです。  
  
```  
virtual BOOL Open(
    LPCTSTR lpszFileName,  
    UINT nOpenFlags,  
    CFileException* pError = NULL);

 
virtual BOOL Open(
    LPCTSTR lpszFileName,  
    UINT nOpenFlags,  
    CAtlTransactionManager* pTM,  
    CFileException* pError = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszFileName`  
 必要なファイルのパスを表す文字列。 相対パスまたは絶対パスができます。  
  
 `nOpenFlags`  
 共有とアクセス モードです。 ファイルを開くときに実行するアクションを指定します。 ビットごとの OR (|) 演算子を使用して、オプションを組み合わせることができます。 1 つのアクセス許可と&1; つの共有オプションが必要です。modeCreate と modeNoInherit モードはオプションです。  
  
 `pError`  
 失敗した操作のステータスを受信する既存のファイルの例外オブジェクトへのポインター。  
  
 `pTM`  
 ポインター、`CAtlTransactionManager`オブジェクトです。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は `TRUE`。それ以外の場合は `FALSE`。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namereadstringa--cstdiofilereadstring"></a><a name="readstring"></a>CStdioFile::ReadString  
 上限に達するまでのバッファーにテキスト データを読み取ります`nMax`–&1; 文字に関連付けられているファイルから、`CStdioFile`オブジェクトです。  
  
```  
virtual LPTSTR ReadString(
    LPTSTR lpsz,  
    UINT nMax);  
  
virtual BOOL ReadString(CString& rString);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpsz`  
 Null で終わる文字列を受信するユーザーが指定したバッファーへのポインターを指定します。  
  
 `nMax`  
 終端の null 文字をカウントせず、読み取る文字の最大数を指定します。  
  
 `rString`  
 参照、`CString`関数が戻るときに、文字列を格納するオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 テキスト データを格納しているバッファーへのポインター。 **NULL**場合はブール値、またはすべてのデータを読み取り中にファイルの終端に達した場合**FALSE**読み取らずに、データ ファイルの終端に達した場合。  
  
### <a name="remarks"></a>コメント  
 最初の改行文字では、読み取りが停止します。 その場合より少ない場合、 `nMax`–&1; 文字が読み取られた、改行文字がバッファーに格納します。 いずれの場合は、null 文字 ('\0') が追加されます。  
  
 [:Read](../../mfc/reference/cfile-class.md#read)はテキスト モードの入力が、それが復帰改行のペアで終了しないにも使用できます。  
  
> [!NOTE]
>  `CString`この関数のバージョンの削除、`'\n'`存在する場合、`LPTSTR`バージョンは含みません。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCFiles #&38;](../../atl-mfc-shared/reference/codesnippet/cpp/cstdiofile-class_2.cpp)]  
  
##  <a name="a-nameseeka--cstdiofileseek"></a><a name="seek"></a>CStdioFile::Seek  
 以前に開いたファイルのポインターを移動します。  
  
```  
virtual ULONGLONG Seek(
    LONGLONG lOff,  
    UINT nFrom);
```  
  
### <a name="parameters"></a>パラメーター  
 `lOff`  
 ポインターを移動するバイト数。  
  
 `nFrom`  
 ポインターの移動モード。 次の値のいずれかを指定する必要があります。  
  
- `CFile::begin`: ファイル ポインターを移動する`lOff`ファイルの先頭からのバイト数を転送します。  
  
- `CFile::current`: ファイル ポインターを移動する`lOff`ファイル内の現在位置からのバイト。  
  
- `CFile::end`: ファイル ポインターを移動する`lOff`ファイルの末尾からのバイト。 なお`lOff`必要がある既存にシークする負ファイル; 正、ファイルの末尾を超える値を求めます。  
  
### <a name="return-value"></a>戻り値  
 要求された位置は、有効な場合`Seek`ファイルの先頭から新しいバイト オフセットを返します。 それ以外の場合、戻り値は未定義と`CFileException`オブジェクトがスローされます。  
  
### <a name="remarks"></a>コメント  
 `Seek`関数を使用するファイルの内容へのランダム アクセス、ポインターを移動して、指定した時間絶対的または相対的です。 データは、検索中に実際には読み込まれません。 要求された位置が、ファイルのサイズよりも大きい場合は、ファイルの長さは、その位置に長くなるし、例外はスローされません。  
  
 ファイルを開いたときに、ファイル ポインターがオフセット 0 で、ファイルの先頭に配置されます。  
  
 この実装の`Seek`ランタイム ライブラリ (CRT) 関数に基づく`fseek`します。 使用状況に関するいくつかの制限がある`Seek`テキスト モードで開いたストリームでします。 詳細については、次を参照してください。 [fseek、_fseeki64](../../c-runtime-library/reference/fseek-fseeki64.md)します。  
  
### <a name="example"></a>例  
 次の例は、使用する方法を示しています。`Seek`の先頭から 1000 バイトのポインターを移動する、`cfile`ファイルです。 なお`Seek`、後で呼び出す必要がありますので、データで読み取られない[CStdioFile::ReadString](#readstring)データを読み取ることです。  
  
 [!code-cpp[NVC_MFCFiles&#39;](../../atl-mfc-shared/reference/codesnippet/cpp/cstdiofile-class_3.cpp)]  
  
##  <a name="a-namewritestringa--cstdiofilewritestring"></a><a name="writestring"></a>CStdioFile::WriteString  
 バッファーからデータに関連付けられているファイルに書き込みます、`CStdioFile`オブジェクトです。  
  
```  
virtual void WriteString(LPCTSTR lpsz);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpsz`  
 Null で終わる文字列を格納しているバッファーへのポインターを指定します。  
  
### <a name="remarks"></a>コメント  
 終端の null 文字 ( `\0`) は、ファイルに書き込まれません。 このメソッドでは、改行文字を書き込みます`lpsz`復帰/改行のペアとしてファイルにします。  
  
 Null で終わるファイルを使用するにはないデータを記述する場合は、`CStdioFile::Write`または[CFile::Write](../../mfc/reference/cfile-class.md#write)します。  
  
 このメソッドは、`CInvalidArgException*`を指定する場合`NULL`の`lpsz`パラメーター。  
  
 このメソッドは、`CFileException*`ファイル システム エラーに応答します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCFiles #&40;](../../atl-mfc-shared/reference/codesnippet/cpp/cstdiofile-class_4.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [CFile クラス](../../mfc/reference/cfile-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CFile クラス](../../mfc/reference/cfile-class.md)   
 [CFile::Duplicate](../../mfc/reference/cfile-class.md#duplicate)   
 [CFile::LockRange](../../mfc/reference/cfile-class.md#lockrange)   
 [CFile::UnlockRange](../../mfc/reference/cfile-class.md#unlockrange)   
 [行わないクラス](../../mfc/reference/cnotsupportedexception-class.md)

