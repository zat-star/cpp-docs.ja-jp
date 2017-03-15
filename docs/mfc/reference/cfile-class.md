---
title: "CFile クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CFile
dev_langs:
- C++
helpviewer_keywords:
- CFile class
- CArchive class, using with CFile
- files [C++], classes for
ms.assetid: b2eb5757-d499-4e67-b044-dd7d1abaa0f8
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
ms.openlocfilehash: bc6edf87e5653a6aa8c749a4574c5b50fdae75a0
ms.lasthandoff: 02/24/2017

---
# <a name="cfile-class"></a>CFile クラス
ファイルに関する MFC の基底クラスです。  
  
## <a name="syntax"></a>構文  
  
```  
class CFile : public CObject  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[ほか](#cfile)|構築、`CFile`パスまたはファイルのハンドルからのオブジェクト。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[解放](#abort)|すべての警告およびエラーを無視してファイルを閉じます。|  
|[データ](#close)|ファイルを閉じたし、オブジェクトを削除します。|  
|[CFile::Duplicate](#duplicate)|このファイルに基づく重複するオブジェクトを構築します。|  
|[CFile::Flush](#flush)|まだが書き込まれるようにデータをフラッシュします。|  
|[CFile::GetFileName](#getfilename)|選択したファイルのファイル名を取得します。|  
|[CFile::GetFilePath](#getfilepath)|選択したファイルのファイルの完全パスを取得します。|  
|[CFile::GetFileTitle](#getfiletitle)|選択したファイルのタイトルを取得します。|  
|[結び付けてその中](#getlength)|ファイルの長さを取得します。|  
|[実行](#getposition)|現在のファイル ポインターを取得します。|  
|[Cfile::getstatus](#getstatus)|静的バージョン、または、開いているファイルの状態を取得、指定したファイル (静的、仮想関数) の状態を取得します。|  
|[CFile::LockRange](#lockrange)|ファイルのバイト数の範囲をロックします。|  
|[CFile::Open](#open)|安全にエラー テスト オプションを使用してファイルを開きます。|  
|[:Read](#read)|現在の位置にあるファイルからの読み取り (バッファー) データ。|  
|[CFile::Remove](#remove)|指定したファイル (静的関数) を削除します。|  
|[CFile::Rename](#rename)|指定したファイル (静的関数) の名前を変更します。|  
|[CFile::Seek](#seek)|現在のファイル ポインターを移動します。|  
|[CFile::SeekToBegin](#seektobegin)|ファイルの先頭には、現在のファイル ポインターを移動します。|  
|[CFile::SeekToEnd](#seektoend)|ファイルの最後に、現在のファイル ポインターを移動します。|  
|[CFile::SetFilePath](#setfilepath)|選択したファイルのファイルの完全パスを設定します。|  
|[CFile::SetLength](#setlength)|ファイルの長さを変更します。|  
|[CFile::SetStatus](#setstatus)|指定したファイル (静的、仮想関数) の状態を設定します。|  
|[CFile::UnlockRange](#unlockrange)|ファイルのバイト数の範囲をロック解除します。|  
|[CFile::Write](#write)|現在のファイル位置のファイルに (バッファー) データを書き込みます。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CFile::operator ハンドル](#operator_handle)|ハンドル、`CFile`オブジェクトです。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CFile::hFileNull](#hfilenull)|かどうかを`CFile`オブジェクトには、有効なハンドル。|  
|[CFile::m_hFile](#m_hfile)|通常、オペレーティング システム ファイル ハンドルが含まれます。|  
  
### <a name="protected-data-members"></a>プロテクト データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CFile::m_pTM](#m_ptm)|ポインター`CAtlTransactionManager`オブジェクトです。|  
  
## <a name="remarks"></a>コメント  
 バッファーを介さずに、バイナリのディスク入力/出力のサービスを直接提供し、間接的にサポート テキスト ファイルとその派生クラスを使用してメモリ ファイル。 `CFile`組み合わせて動作、 `CArchive` Microsoft Foundation Class のオブジェクトのシリアル化をサポートするクラス。  
  
 このクラスとその派生クラス間の階層関係では、プログラム、ポリモーフィックですべてのファイル オブジェクトを操作する`CFile`インターフェイスです。 メモリ ファイルは、たとえば、ディスク ファイルと同様に動作します。  
  
 使用する`CFile`とその派生クラスの汎用的なディスク I/O です。 使用`ofstream`またはディスク ファイルに送信される書式設定されたテキストの他の Microsoft iostream クラスです。  
  
 通常、ディスク ファイルを開く時に自動的に`CFile`構築と破棄を終了します。 静的メンバー関数を使用して、ファイルを開くことがなく、ファイルの状態を問い合わせることです。  
  
 使用する方法について`CFile`、記事を参照して[MFC のファイル](../../mfc/files-in-mfc.md)と[ファイル処理](../../c-runtime-library/file-handling.md)で、*ランタイム ライブラリ リファレンス*します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CFile`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afx.h  
  
##  <a name="a-nameaborta--cfileabort"></a><a name="abort"></a>解放  
 このオブジェクトに関連付けられているファイルを閉じ、ファイルを読み取りまたは書き込みが使用できなくなります。  
  
```  
virtual void Abort();
```  
  
### <a name="remarks"></a>コメント  
 オブジェクトを破棄する前に、ファイルを終了しなかった場合、デストラクターがファイルを閉じます。  
  
 例外を処理するときに`CFile::Abort`異なる`CFile::Close`の&2; つの重要な点です。 1 つは、**中止**関数が例外をスローしませんの障害に関するによってエラーが無視されるため**中止**します。 2 番目、**中止**されません**ASSERT**ファイルが開かれていない、または以前に閉じられました。  
  
 使用した場合**新しい**を割り当てる、`CFile`ヒープのオブジェクトの後に、ファイルを閉じて後に削除する必要があります。 **Abort** sets `m_hFile` to `CFile::hFileNull`.  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCFiles&#5;](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_1.cpp)]  
  
##  <a name="a-namecfilea--cfilecfile"></a><a name="cfile"></a>ほか  
 `CFile` オブジェクトを構築して初期化します。  
  
```  
CFile();  
CFile(CAtlTransactionManager* pTM);  
  CFile(HANDLE hFile);

 
CFile(
LPCTSTR lpszFileName,  
UINT nOpenFlags);

 
CFile(
LPCTSTR lpszFileName,  
UINT nOpenFlags,  
CAtlTransactionManager* pTM);
```  
  
### <a name="parameters"></a>パラメーター  
 `hFile`  
 `CFile` オブジェクトにアタッチするためのファイル ハンドル。  
  
 `lpszFileName`  
 
          `CFile` オブジェクトにアタッチするための相対パスまたは完全パス。  
  
 `nOpenFlags`  
 指定されたファイルのファイル アクセス オプションのビットごとの組み合わせ (OR)。 使用できるオプションについては、「解説」を参照してください。  
  
 `pTM`  
 CAtlTransactionManager オブジェクトへのポインター。  
  
### <a name="remarks"></a>コメント  
 次の&5; つの表は、`nOpenFlags` パラメーターの、使用できるオプションを示しています。  
  
 次のファイル アクセス モード オプションから&1; つのみ選択します。 既定のファイル アクセス モードは `CFile::modeRead` であり、これは読み取り専用です。  
  
|値|説明|  
|-----------|-----------------|  
|`CFile::modeRead`|読み取りアクセスのみを要求します。|  
|`CFile::modeWrite`|書き込みアクセスのみを要求します。|  
|`CFile::modeReadWrite`|読み取りおよび書き込みアクセスを要求します。|  
  
 次の文字モード オプションのいずれかを選択します。  
  
|値|説明|  
|-----------|-----------------|  
|`CFile::typeBinary`|バイナリ モードを設定します (派生クラスのみで使用されます)。|  
|`CFile::typeText`|キャリッジ リターンとライン フィードのペアの特殊な処理を含むテキスト モードを設定します (派生クラスのみで使用されます)。|  
|`CFile::typeUnicode`|Unicode モードを設定します (派生クラスのみで使用されます)。 アプリケーションが Unicode 構成でビルドされた場合、テキストは Unicode 形式でファイルに書き込まれます。 BOM はファイルに書き込まれません。|  
  
 次のファイル共有モード オプションから&1; つのみ選択します。 既定のファイル共有モードは `CFile::shareExclusive` であり、これは排他的です。  
  
|値|説明|  
|-----------|-----------------|  
|`CFile::shareDenyNone`|共有の制限はありません。|  
|`CFile::shareDenyRead`|他のすべての読み取りアクセスを拒否します。|  
|`CFile::shareDenyWrite`|他のすべての書き込みアクセスを拒否します。|  
|`CFile::shareExclusive`|他のすべての読み取りおよび書き込みアクセスを拒否します。|  
  
 次のファイル作成モード オプションから最初のオプションまたは両方を選択します。 既定の作成モードは `CFile::modeNoTruncate` であり、これは既存を開くです。  
  
|値|説明|  
|-----------|-----------------|  
|`CFile::modeCreate`|ファイルが存在しない場合は、新しいファイルを作成します。 です。ファイルが既に存在する場合[CFileException](../../mfc/reference/cfileexception-class.md)が発生します。|  
|`CFile::modeNoTruncate`|ファイルが存在しない場合は新しいファイルを作成します。ファイルが既に存在する場合は、そのファイルが `CFile` オブジェクトにアタッチされます。|  
  
 説明に従って次のファイル キャッシュ オプションを選択します。 既定では、オプションとしては選択できない汎用のキャッシュ スキームが使用されます。  
  
|値|説明|  
|-----------|-----------------|  
|`CFile::osNoBuffer`|ファイルの中間キャッシュは使用されません。 このオプションを選択すると、次の 2 つのオプションは取り消されます。|  
|`CFile::osRandomAccess`|ファイル キャッシュはランダム アクセスに対して最適化されます。 このオプションと順次スキャン オプションを一緒に使用しないでください。|  
|`CFile::osSequentialScan`|ファイル キャッシュは順次アクセスに対して最適化されます。 このオプションとランダム アクセス オプションを一緒に使用しないでください。|  
|`CFile::osWriteThrough`|書き込み操作が遅延なしで実行されます。|  
  
 ファイル ハンドルが継承されないようにするために、次のセキュリティ オプションを選択します。 既定では、新しい子プロセスはファイル ハンドルを使用できます。  
  
|値|説明|  
|-----------|-----------------|  
|`CFile::modeNoInherit`|子プロセスがファイル ハンドルを使用できないようにします。|  
  
 既定のコンストラクターでは、メンバーは初期化されますが、ファイルは `CFile` オブジェクトにアタッチされません。 このコンス トラクターを使用すると、使用、 [CFile::Open](#open)ファイルを開きにアタッチする方法、`CFile`オブジェクトです。  
  
 1 つのパラメーターを持つコンストラクターでは、メンバーは初期化され、既存のファイルが `CFile` オブジェクトにアタッチされます。  
  
 2 つのパラメーターを持つコンストラクターでは、メンバーは初期化され、指定されたファイルを開くことが試行されます。 このコンストラクターによって、指定されたファイルが正常に開かれると、ファイルは `CFile` オブジェクトにアタッチされます。それ以外の場合は、このコンストラクターによって `CInvalidArgException` オブジェクトへのポインターがスローされます。 例外を処理する方法の詳細については、次を参照してください。[例外](../../mfc/exception-handling-in-mfc.md)します。  
  
 `CFile` オブジェクトによって、指定されたファイルが正常に開かれた場合、このファイルは `CFile` オブジェクトが破棄されたときに自動的に閉じられます。それ以外の場合は、`CFile` オブジェクトにアタッチされなくなった後でファイルを明示的に閉じる必要があります。  
  
### <a name="example"></a>例  
 `CFile` の使用例を次のコードに示します。  
  
 [!code-cpp[NVC_MFCFiles&4;](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_2.cpp)]  
  
##  <a name="a-nameclosea--cfileclose"></a><a name="close"></a>データ  
 このオブジェクトに関連付けられているファイルを閉じ、ファイルを読み取りまたは書き込みが使用できなくなります。  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>コメント  
 オブジェクトを破棄する前に、ファイルを終了しなかった場合、デストラクターがファイルを閉じます。  
  
 使用した場合**新しい**を割り当てる、`CFile`ヒープのオブジェクトの後に、ファイルを閉じて後に削除する必要があります。 **Close** sets `m_hFile` to `CFile::hFileNull`.  
  
### <a name="example"></a>例  
 例を参照してください[ほか](#cfile)します。  
  
##  <a name="a-nameduplicatea--cfileduplicate"></a><a name="duplicate"></a>CFile::Duplicate  
 重複する構成体`CFile`指定されたファイルのオブジェクト。  
  
```  
virtual CFile* Duplicate() const;  
```  
  
### <a name="return-value"></a>戻り値  
 重複するへのポインター`CFile`オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 これは、C ランタイム関数と同じ`_dup`します。  
  
##  <a name="a-nameflusha--cfileflush"></a><a name="flush"></a>CFile::Flush  
 ファイルに書き込まれるファイル バッファーの残りの部分を強制します。  
  
```  
virtual void Flush();
```  
  
### <a name="remarks"></a>コメント  
 使用`Flush`のフラッシュを保証しません`CArchive`バッファー。 アーカイブを使用している場合に呼び出す[ときは](../../mfc/reference/carchive-class.md#flush)最初です。  
  
### <a name="example"></a>例  
 例を参照してください[CFile::SetFilePath](#setfilepath)します。  
  
##  <a name="a-namegetfilenamea--cfilegetfilename"></a><a name="getfilename"></a>CFile::GetFileName  
 指定したファイルの名前を取得するには、このメンバー関数を呼び出します。  
  
```  
virtual CString GetFileName() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ファイルの名前です。  
  
### <a name="remarks"></a>コメント  
 たとえば、呼び出す`GetFileName`ファイルについてユーザーにメッセージを生成する`c:\windows\write\myfile.wri`、ファイル名、`myfile.wri`が返されます。  
  
 名を含むファイルの完全パスを返すには、呼び出す[まで含めた](#getfilepath)します。 ファイルのタイトルを取得する ( `myfile`)、呼び出す[GetFileTitle](#getfiletitle)します。  
  
### <a name="example"></a>例  
 次のコード片では、システムが開きます。WINDOWS ディレクトリに INI ファイルです。 かどうかは、例では、出力されます名前とパス、タイトル、出力で示されています。  
  
 [!code-cpp[NVC_MFCFiles&6;](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_3.cpp)]  
  
##  <a name="a-namegetfilepatha--cfilegetfilepath"></a><a name="getfilepath"></a>CFile::GetFilePath  
 指定されたファイルの完全なパスを取得するには、このメンバー関数を呼び出します。  
  
```  
virtual CString GetFilePath() const;  
```  
  
### <a name="return-value"></a>戻り値  
 指定したファイルの完全パス。  
  
### <a name="remarks"></a>コメント  
 たとえば、呼び出す`GetFilePath`ファイルについてユーザーにメッセージを生成する`c:\windows\write\myfile.wri`、ファイルのパス`c:\windows\write\myfile.wri`が返されます。  
  
 ファイルの名前だけを返す ( `myfile.wri`)、呼び出す[GetFileName](#getfilename)します。 ファイルのタイトルを取得する ( `myfile`)、呼び出す[GetFileTitle](#getfiletitle)します。  
  
### <a name="example"></a>例  
 例を参照してください[GetFileName](#getfilename)します。  
  
##  <a name="a-namegetfiletitlea--cfilegetfiletitle"></a><a name="getfiletitle"></a>CFile::GetFileTitle  
 ファイルのファイルのタイトル (表示名) を取得するには、このメンバー関数を呼び出します。  
  
```  
virtual CString GetFileTitle() const;  
```  
  
### <a name="return-value"></a>戻り値  
 基になるファイルのタイトルです。  
  
### <a name="remarks"></a>コメント  
 このメソッドを呼び出す[GetFileTitle](http://msdn.microsoft.com/library/windows/desktop/ms646924)ファイルのタイトルを取得します。 成功した場合、メソッドは、システムは、ファイル名をユーザーに表示を使用して文字列を返します。 それ以外の場合、メソッド呼び出し[PathFindFileName](http://msdn.microsoft.com/library/windows/desktop/bb773589)を基になるファイルのファイル名 (ファイル拡張子を含む) を取得します。 そのため、返されるファイル タイトル文字列にファイル拡張子が含まれません常にあります。 詳細については、次を参照してください。 [GetFileTitle](http://msdn.microsoft.com/library/windows/desktop/ms646924)と[PathFindFileName](http://msdn.microsoft.com/library/windows/desktop/bb773589)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 名を含むファイルの完全パスを返すには、呼び出す[まで含めた](#getfilepath)します。 ファイルの名前だけを返すを呼び出す[GetFileName](#getfilename)します。  
  
### <a name="example"></a>例  
 例を参照してください[GetFileName](#getfilename)します。  
  
##  <a name="a-namegetlengtha--cfilegetlength"></a><a name="getlength"></a>結び付けてその中  
 現在の論理ファイルのバイトの長さを取得します。  
  
```  
virtual ULONGLONG GetLength() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ファイルの長さ。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCFiles&#7;](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_4.cpp)]  
  
##  <a name="a-namegetpositiona--cfilegetposition"></a><a name="getposition"></a>実行  
 ファイル ポインターは、以降の呼び出しで使用できるは、現在の値を取得する`Seek`です。  
  
```  
virtual ULONGLONG GetPosition() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ファイルのポインター。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCFiles&#8;](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_5.cpp)]  
  
##  <a name="a-namegetstatusa--cfilegetstatus"></a><a name="getstatus"></a>Cfile::getstatus  
 このメソッドに関連するステータス情報を取得する指定された`CFile`オブジェクト インスタンスまたは指定されたファイル パス。  
  
```  
BOOL GetStatus(CFileStatus& rStatus) const;  
  
static BOOL PASCAL GetStatus(
    LPCTSTR lpszFileName,  
    CFileStatus& rStatus,
    CAtlTransactionManager* pTM = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `rStatus`  
 ユーザーが指定したへの参照を**CFileStatus**は状態情報を受信する構造体。 **CFileStatus**構造体には、次のフィールド。  
  
- **CTime m_ctime**ファイルが作成された日付と時刻。  
  
- **CTime m_mtime**ファイルが最後に変更された日時。  
  
- **CTime m_atime**読み取り用、ファイルの最終アクセス日時。  
  
- **使い m_size** (バイト単位) DIR コマンドによって報告されたファイルの論理サイズ。  
  
- **バイト m_attribute**ファイルの属性のバイト。  
  
- **m_szFullName [_MAX_PATH] char** Windows 文字セット内の絶対ファイル名。  
  
 `lpszFileName`  
 Windows の文字の文字列はパスに設定して目的のファイルです。 パスには、相対パスまたは絶対、またはネットワーク パス名を含めることができます。  
  
 `pTM`  
 CAtlTransactionManager オブジェクトへのポインター。  
  
### <a name="return-value"></a>戻り値  
 **TRUE**場合は、指定したファイルのステータス情報が正常に取得した以外の場合、 **FALSE**します。  
  
### <a name="remarks"></a>コメント  
 静的でないバージョンの**GetStatus**に関連付けられている、開いているファイルのステータス情報を取得、指定された`CFile`オブジェクトです。  静的バージョン**GetStatus**実際には、ファイルを開くことがなく、指定されたファイル パスからファイルの状態を取得します。 これは、ファイルの存在とアクセス権を調べるに便利です。  
  
 **M_attribute**のメンバー、 **CFileStatus**構造は、ファイルの属性セットを参照します。 `CFile`クラスには、**属性**列挙型のため、ファイル属性を記号として指定することができます。  
  
 `enum Attribute {`  
  
 `normal =    0x00,`  
  
 `readOnly =  0x01,`  
  
 `hidden =    0x02,`  
  
 `system =    0x04,`  
  
 `volume =    0x08,`  
  
 `directory = 0x10,`  
  
 `archive =   0x20`  
  
 `};`  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCFiles&#10;](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_6.cpp)]  
  
##  <a name="a-namehfilenulla--cfilehfilenull"></a><a name="hfilenull"></a>CFile::hFileNull  
 有効なファイル ハンドルの存在の決定、`CFile`オブジェクトです。  
  
```  
static AFX_DATA const HANDLE hFileNull;  
```  
  
### <a name="remarks"></a>コメント  
 この定数はかどうかを使用、`CFile`オブジェクトが有効なファイル ハンドル。  
  
 次の例では、この操作を示します。  
  
 [!code-cpp[NVC_MFCFiles #&22;](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_7.cpp)]  
  
##  <a name="a-namelockrangea--cfilelockrange"></a><a name="lockrange"></a>CFile::LockRange  
 ファイルを開き、ファイルが既にロックされている場合、例外がスローのバイト数の範囲をロックします。  
  
```  
virtual void LockRange(
    ULONGLONG dwPos,  
    ULONGLONG dwCount);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwPos`  
 ロックするバイト範囲の先頭のバイト オフセット。  
  
 `dwCount`  
 ロックする範囲のバイト数。  
  
### <a name="remarks"></a>コメント  
 ファイル内のバイトをロックすると、他のプロセスがそれらのバイトにアクセスできなくなります。 ファイルの&1; つ以上の領域をロックすることができますが、重なり合う領域は使用できません。  
  
 使用して、地域のロックを解除するときに、`UnlockRange`メンバー関数をこのバイト範囲は、以前にロックされた領域と正確に一致する必要があります。 `LockRange`関数は、隣接する領域を結合しません。 ロックされている&2; つの領域が隣接している場合は、必要がありますロックを解除する各地域とは別にします。  
  
> [!NOTE]
>  この関数は、 `CMemFile`-クラスを派生します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCFiles&#12;](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_8.cpp)]  
  
##  <a name="a-namemhfilea--cfilemhfile"></a><a name="m_hfile"></a>CFile::m_hFile  
 開いているファイルのオペレーティング システム ファイル ハンドルが含まれています。  
  
```  
HANDLE m_hFile;  
```  
  
### <a name="remarks"></a>コメント  
 `m_hFile`型のパブリック変数**UINT**します。 含まれている`CFile::hFileNull`(空のファイルをオペレーティング システム独立インジケーター) のハンドルが割り当てられていない場合。  
  
 使用`m_hFile`はメンバーの意味は、派生クラスによって異なりますのでお勧めしません。 `m_hFile`クラスを使用して非ポリモーフィックなサポートするうえで利便性のパブリック メンバーになります。  
  
##  <a name="a-namemptma--cfilemptm"></a><a name="m_ptm"></a>CFile::m_pTM  
 ポインター、`CAtlTransactionManager`オブジェクトです。  
  
```  
CAtlTransactionManager* m_pTM;  
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameopena--cfileopen"></a><a name="open"></a>CFile::Open  
 オーバーロードされます。 **開いている**は、既定で使用するために設計されています`CFile`コンス トラクターです。  
  
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
 必要なファイルのパスを表す文字列。 相対パス、絶対パス、またはネットワーク名 (UNC) パスができます。  
  
 `nOpenFlags`  
 A **UINT**ファイルの共有とアクセス モードを定義します。 ファイルを開くときに実行するアクションを指定します。 ビットごとの OR を使用してオプションを組み合わせることができます ( **|** ) 演算子。 1 つのアクセス許可と&1; つの共有オプションが必要です。**modeCreate**と**modeNoInherit**モードは省略可能です。 参照してください、 [CFile](#cfile)モード オプションの一覧のコンス トラクターです。  
  
 `pError`  
 失敗した操作のステータスを受信する既存のファイルの例外オブジェクトへのポインター。  
  
 `pTM`  
 CAtlTransactionManager オブジェクトへのポインター。  
  
### <a name="return-value"></a>戻り値  
 Open が成功した場合は 0 以外。それ以外の場合 0 を返します。 `pError`パラメーターは 0 が返される場合にのみ意味を持ちます。  
  
### <a name="remarks"></a>コメント  
 2 つの関数は、通常は失敗ファイルを開くための「安全」メソッドを形成します。  
  
 中に、`CFile`コンス トラクターは、エラー状態で例外をスロー**開いている**戻ります**FALSE**エラー条件にします。 **開いている**初期化できますが、 [CFileException](../../mfc/reference/cfileexception-class.md)ただし、エラーを記述するオブジェクト。 指定しない場合、`pError`パラメーター、またはを渡した場合**NULL**の`pError`、**開いている**戻ります**FALSE**をスローしないと、`CFileException`です。 既存のポインターを渡す場合`CFileException`と**開く**エラーを検出すると、関数によって内容が設定は、そのエラーを示す情報。 いずれにしてもで**開く**例外をスローします。  
  
 次の表に、想定される結果**開く**します。  
  
|`pError`|エラーが発生しました|戻り値|未定義のままコンテンツ|  
|--------------|------------------------|------------------|----------------------------|  
|**NULL**|いいえ|**TRUE**|適用なし|  
|ポインター`CFileException`|いいえ|**TRUE**|変更なし|  
|**NULL**|はい|**FALSE**|適用なし|  
|ポインター`CFileException`|はい|**FALSE**|初期化エラーを記述するには|  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCFiles&#13;](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_9.cpp)]  
  
 [!code-cpp[NVC_MFCFiles&#14;](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_10.cpp)]  
  
##  <a name="a-nameoperatorhandlea--cfileoperator-handle"></a><a name="operator_handle"></a>CFile::operator ハンドル  
 この演算子を識別するハンドルを使用して、`CFile`などの関数オブジェクト[ReadFileEx](http://msdn.microsoft.com/library/windows/desktop/aa365468)と[GetFileTime](http://msdn.microsoft.com/library/windows/desktop/ms724320)予想される、`HANDLE`です。  
  
```  
operator HANDLE() const;  
```  
  
##  <a name="a-namereada--cfileread"></a><a name="read"></a>:Read  
 関連付けられているファイルからバッファーにデータを読み取り、`CFile`オブジェクトです。  
  
```  
virtual UINT Read(
    void* lpBuf,  
    UINT nCount);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpBuf`  
 ファイルから読み取られたデータを受信するユーザーが指定したバッファーへのポインター。  
  
 `nCount`  
 ファイルから読み取るバイトの最大数。 テキスト モードのファイルには、キャリッジ リターンとライン フィードのペアが&1; つの文字としてカウントされます。  
  
### <a name="return-value"></a>戻り値  
 バッファーに転送するバイト数。 すべての`CFile`クラス、戻り値がありますより小さい`nCount`ファイルの末尾に達した場合。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCFiles&#15;](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_11.cpp)]  
  
 別の例を参照してください。 [CFile::Open](#open)します。  
  
##  <a name="a-nameremovea--cfileremove"></a><a name="remove"></a>CFile::Remove  
 この静的関数では、パスで指定されたファイルを削除します。  
  
```  
static void PASCAL Remove(
    LPCTSTR lpszFileName, 
    CAtlTransactionManager* pTM = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszFileName`  
 必要なファイルのパスを表す文字列。 パスは相対パスまたは絶対とネットワーク名を含めることができます。  
  
 `pTM`  
 CAtlTransactionManager オブジェクトへのポインター。  
  
### <a name="remarks"></a>コメント  
 ディレクトリは削除されません。  
  
 **削除**接続されているファイルが開いている場合、またはファイルを削除できない場合、メンバー関数が例外をスローします。 これは、DEL コマンドに相当します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCFiles&17;](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_12.cpp)]  
  
##  <a name="a-namerenamea--cfilerename"></a><a name="rename"></a>CFile::Rename  
 この静的関数は、指定したファイルの名前を変更します。  
  
```  
static void PASCAL Rename(
    LPCTSTR lpszOldName,  
    LPCTSTR lpszNewName,  
    CAtlTransactionManager* pTM = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszOldName`  
 以前のパス。  
  
 `lpszNewName`  
 新しいパス。  
  
 `pTM`  
 CAtlTransactionManager オブジェクトへのポインター。  
  
### <a name="remarks"></a>コメント  
 ディレクトリの名前を変更することはできません。 これは、REN コマンドに相当します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCFiles&#18;](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_13.cpp)]  
  
##  <a name="a-nameseeka--cfileseek"></a><a name="seek"></a>CFile::Seek  
 開いているファイルのファイル ポインターを移動します。  
  
```  
virtual ULONGLONG Seek(
LONGLONG lOff,  
UINT nFrom);
```  
  
### <a name="parameters"></a>パラメーター  
 `lOff`  
 ファイル ポインターを移動するバイト数。 正の値は、ファイルの終わりに向かってファイル ポインターを移動します。負の値は、ファイルの先頭に向かってファイル ポインターを移動します。  
  
 `nFrom`  
 シークを開始する位置。 指定できる値については、「解説」を参照してください。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は、ファイル ポインターの位置それ以外の場合、戻り値は未定義とへのポインター、`CFileException`例外がスローされます。  
  
### <a name="remarks"></a>コメント  
 次の表に、可能な値、`nFrom`パラメーター。  
  
|値|説明|  
|-----------|-----------------|  
|`CFile::begin`|ファイルの先頭から検索します。|  
|`CFile::current`|ファイル ポインターの現在の場所から検索します。|  
|`CFile::end`|ファイルの末尾から検索します。|  
  
 ファイルを開いたときに、ファイル ポインターは 0 で、ファイルの先頭に配置されます。  
  
 ファイル ポインターは、ファイルの末尾を越えた位置を設定できます。 これを行う場合、ファイルのサイズは、ファイルに書き込むまで増加しません。  
  
 このメソッドの例外ハンドラーは、例外が処理された後、例外オブジェクトを削除する必要があります。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCFiles&#9;](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_14.cpp)]  
  
##  <a name="a-nameseektobegina--cfileseektobegin"></a><a name="seektobegin"></a>CFile::SeekToBegin  
 ファイルの先頭には、ファイル ポインターの値を設定します。  
  
```  
void SeekToBegin();
```  
  
### <a name="remarks"></a>コメント  
 `SeekToBegin()` は `Seek( 0L, CFile::begin )` と同じです。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCFiles&#19;](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_15.cpp)]  
  
##  <a name="a-nameseektoenda--cfileseektoend"></a><a name="seektoend"></a>CFile::SeekToEnd  
 論理上、ファイルの末尾にファイル ポインターの値を設定します。  
  
```  
ULONGLONG SeekToEnd();
```  
  
### <a name="return-value"></a>戻り値  
 ファイルの長さをバイト単位で返します。  
  
### <a name="remarks"></a>コメント  
 `SeekToEnd()` は `CFile::Seek( 0L, CFile::end )` と同じです。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCFiles&#19;](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_15.cpp)]  
  
##  <a name="a-namesetfilepatha--cfilesetfilepath"></a><a name="setfilepath"></a>CFile::SetFilePath  
 ファイルのパスを指定するには、この関数を呼び出すたとえば、次の場合、ファイルのパスは使用できません、 [CFile](../../mfc/reference/cfile-class.md)を呼び出すオブジェクトを構築する必要が`SetFilePath`を提供します。  
  
```  
virtual void SetFilePath(LPCTSTR lpszNewName);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszNewName`  
 新しいパスを指定する文字列へのポインター。  
  
### <a name="remarks"></a>コメント  
  
> [!NOTE]
> `SetFilePath`いないファイルを開くか、ファイルを作成しません。単に関連付ける、`CFile`オブジェクトを使用してパス名を使用します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCFiles&#20;](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_16.cpp)]  
  
##  <a name="a-namesetlengtha--cfilesetlength"></a><a name="setlength"></a>CFile::SetLength  
 ファイルの長さを変更するには、この関数を呼び出します。  
  
```  
virtual void SetLength(ULONGLONG dwNewLen);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwNewLen`  
 目的のファイルのバイトの長さ。 この値は、ファイルの現在の長さより大きくまたは小さくできます。 ファイルは拡張か、必要に応じて切り捨てられます。  
  
### <a name="remarks"></a>コメント  
  
> [!NOTE]
>  `CMemFile`、この関数は、`CMemoryException`オブジェクトです。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCFiles&#11;](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_17.cpp)]  
  
##  <a name="a-namesetstatusa--cfilesetstatus"></a><a name="setstatus"></a>CFile::SetStatus  
 このファイルの場所に関連付けられているファイルの状態を設定します。  
  
```  
static void PASCAL SetStatus(
    LPCTSTR lpszFileName,  
    const CFileStatus& status,  
    CAtlTransactionManager* pTM = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszFileName`  
 必要なファイルのパスを表す文字列。 パスは相対パスまたは絶対とネットワーク名を含めることができます。  
  
 *status*  
 新しいステータス情報を保持するバッファー。 呼び出す、 **GetStatus**自動的に入力するメンバー関数を**CFileStatus** 、現在の値を構成し、必要に応じて変更を加えます。 値が 0 の場合、対応する状態の項目は更新されません。 参照してください、 [GetStatus](#getstatus)メンバー関数の詳細については、 **CFileStatus**構造体。  
  
 `pTM`  
 CAtlTransactionManager オブジェクトへのポインター。  
  
### <a name="remarks"></a>コメント  
 時間を設定するには、変更、 **m_mtime**フィールド*ステータス*します。  
  
 呼び出しを行うことに注意してください`SetStatus`をファイルの属性のみを変更するために、 **m_mtime**ファイルの状態の構造体のメンバーがゼロ以外、属性もを受ける可能性 (スタンプでは、属性に副作用があります、時刻の変更)。 最初に設定ファイルの属性だけを変更する場合、 **m_mtime** 、ファイルの状態構造体のメンバーがゼロにへの呼び出しを行う`SetStatus`します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCFiles #&21;](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_18.cpp)]  
  
##  <a name="a-nameunlockrangea--cfileunlockrange"></a><a name="unlockrange"></a>CFile::UnlockRange  
 開いているファイルのバイト数の範囲をロック解除します。  
  
```  
virtual void UnlockRange(
    ULONGLONG dwPos,  
    ULONGLONG dwCount);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwPos`  
 ロックを解除するには、このバイト範囲の先頭のバイト オフセット。  
  
 `dwCount`  
 ロックを解除する範囲のバイト数。  
  
### <a name="remarks"></a>コメント  
 説明を参照して、 [LockRange](#lockrange)詳細については、メンバー関数。  
  
> [!NOTE]
>  この関数は、 `CMemFile`-クラスを派生します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCFiles&#12;](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_8.cpp)]  
  
##  <a name="a-namewritea--cfilewrite"></a><a name="write"></a>CFile::Write  
 バッファーからデータに関連付けられているファイルに書き込みます、`CFile`オブジェクトです。  
  
```  
virtual void Write(
    const void* lpBuf,  
    UINT nCount);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpBuf`  
 ファイルに書き込まれるデータを格納しているユーザーが指定したバッファーへのポインター。  
  
 `nCount`  
 バッファーからの転送バイト数。 テキスト モードのファイルには、キャリッジ リターンとライン フィードのペアが&1; つの文字としてカウントされます。  
  
### <a name="remarks"></a>コメント  
 **書き込み**ディスクの空き容量の条件を含むいくつかの条件への応答で例外をスローします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCFiles&#16;](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_19.cpp)]  
  
 さらに、例を参照[ほか](#cfile)と[CFile::Open](#open)します。  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル DRAWCLI](../../visual-cpp-samples.md)   
 [CObject クラス](../../mfc/reference/cobject-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CStdioFile クラス](../../mfc/reference/cstdiofile-class.md)   
 [CMemFile クラス](../../mfc/reference/cmemfile-class.md)

