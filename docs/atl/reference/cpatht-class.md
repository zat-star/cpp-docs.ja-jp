---
title: "CPathT クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CPathT
- CPathT
- ATL::CPathT<StringType>
- ATL::CPathT
- ATL.CPathT<StringType>
dev_langs:
- C++
helpviewer_keywords:
- CPathT class
ms.assetid: eba4137d-1fd2-4b44-a2e1-0944db64df3c
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
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 8cbd91ae1c4318788b38b2daaa7721d1a29fca98
ms.lasthandoff: 02/24/2017

---
# <a name="cpatht-class"></a>CPathT クラス
このクラスは、パスを表します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template <typename StringType>
class CPathT
```  
  
#### <a name="parameters"></a>パラメーター  
 `StringType`  
 パスを使用する ATL と MFC string クラス (参照[CStringT](../../atl-mfc-shared/reference/cstringt-class.md))。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-typedefs"></a>パブリック typedef  
  
|名前|説明|  
|----------|-----------------|  
|[CPathT::PCXSTR](#pcxstr)|文字列定数の型。|  
|[CPathT::PXSTR](#pxstr)|文字列型です。|  
|[CPathT::XCHAR](#xchar)|文字型です。|  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CPathT::CPathT](#cpatht)|パスのコンス トラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CPathT::AddBackslash](#addbackslash)|パスの正しい構文を作成するための文字列の末尾に円記号を追加するには、このメソッドを呼び出します。|  
|[CPathT::AddExtension](#addextension)|パスにファイル拡張子を追加するには、このメソッドを呼び出します。|  
|[CPathT::Append](#append)|現在のパスに文字列を追加するには、このメソッドを呼び出します。|  
|[CPathT::BuildRoot](#buildroot)|特定のドライブ数からルートのパスを作成するには、このメソッドを呼び出します。|  
|[CPathT::Canonicalize](#canonicalize)|パスを正規の形式に変換するには、このメソッドを呼び出します。|  
|[CPathT::Combine](#combine)|ディレクトリ名を表す文字列とファイルのパス名を&1; つのパスを表す文字列を連結するには、このメソッドを呼び出します。|  
|[CPathT::CommonPrefix](#commonprefix)|指定されたパスが現在のパスと共通プレフィックスを共有するかどうかを判断するには、このメソッドを呼び出します。|  
|[CPathT::CompactPath](#compactpath)|省略記号をパス コンポーネントを置き換えることで、指定したピクセル幅に収まるようにファイル パスを短くには、このメソッドを呼び出します。|  
|[CPathT::CompactPathEx](#compactpathex)|省略記号をパス コンポーネントを置き換えることで、指定した文字数に収まるようにファイル パスを短くには、このメソッドを呼び出します。|  
|[CPathT::FileExists](#fileexists)|このメソッドでは、このパス名でファイルが存在するかどうかを確認します。|  
|[CPathT::FindExtension](#findextension)|パス内のファイル拡張子の位置を検索するには、このメソッドを呼び出します。|  
|[CPathT::FindFileName](#findfilename)|パス内のファイル名の位置を検索するには、このメソッドを呼び出します。|  
|[CPathT::GetDriveNumber](#getdrivenumber)|このメソッドを呼び出して 'Z' を 'A' の範囲内のドライブ文字のパスを検索し、対応するドライブの数を返します。|  
|[CPathT::GetExtension](#getextension)|パスからファイルの拡張子を取得するには、このメソッドを呼び出します。|  
|[CPathT::IsDirectory](#isdirectory)|パスが有効なディレクトリであるかどうかを確認するには、このメソッドを呼び出します。|  
|[CPathT::IsFileSpec](#isfilespec)|パス区切り文字のパスを検索するには、このメソッドを呼び出す (たとえば、':' または '\\')。 パス区切り文字がない場合、パスがファイルの仕様のパスと見なされます。|  
|[CPathT::IsPrefix](#isprefix)|パスにによって渡される種類の有効なプレフィックスが含まれるかどうか確認するには、このメソッドを呼び出す`pszPrefix`します。|  
|[CPathT::IsRelative](#isrelative)|このメソッドでは、パスが相対かを判断します。|  
|[CPathT::IsRoot](#isroot)|パスがディレクトリのルートであるかを判断するには、このメソッドを呼び出します。|  
|[CPathT::IsSameRoot](#issameroot)|別のパスが現在のパスと、共通のルート コンポーネントを持つかどうかを判断するには、このメソッドを呼び出します。|  
|[CPathT::IsUNC](#isunc)|パスが、サーバーの有効な UNC (汎用名前付け規則) パスであるかどうかを確認するには、このメソッドを呼び出すし、共有します。|  
|[CPathT::IsUNCServer](#isuncserver)|このメソッドでは、パスがサーバーだけを表す有効な UNC (汎用名前付け規則) パスであるかどうかを確認します。|  
|[CPathT::IsUNCServerShare](#isuncservershare)|パスが有効な UNC (汎用名前付け規則) 共有パスであるかどうかを確認するには、このメソッドを呼び出す\\ \  *server*\ *共有*します。|  
|[CPathT::MakePretty](#makepretty)|パスをパスの外観を一貫性のある文字をすべて小文字に変換するには、このメソッドを呼び出します。|  
|[CPathT::MatchSpec](#matchspec)|ワイルドカード一致の種類を含む文字列へのパスを検索するには、このメソッドを呼び出します。|  
|[CPathT::QuoteSpaces](#quotespaces)|このメソッドを呼び出して、スペースが含まれている場合は、パスを引用符で囲みます。|  
|[CPathT::RelativePathTo](#relativepathto)|1 つのファイルまたはフォルダーから別の相対パスを作成するには、このメソッドを呼び出します。|  
|[CPathT::RemoveArgs](#removeargs)|パスから、コマンドライン引数を削除するには、このメソッドを呼び出します。|  
|[CPathT::RemoveBackslash](#removebackslash)|パスから、末尾に円記号を削除するには、このメソッドを呼び出します。|  
|[CPathT::RemoveBlanks](#removeblanks)|パスのすべての先頭および末尾のスペースを削除するには、このメソッドを呼び出します。|  
|[CPathT::RemoveExtension](#removeextension)|1 つを使用する必要がある場合は、パスからファイルの拡張子を削除するには、このメソッドを呼び出します。|  
|[CPathT::RemoveFileSpec](#removefilespec)|それらがある場合は、パスの末尾にファイル名と円記号を削除するには、このメソッドを呼び出します。|  
|[CPathT::RenameExtension](#renameextension)|このメソッドを呼び出して、新しい拡張機能で、パスにファイル名拡張子を置き換えます。 ファイル名に拡張子が含まれていない場合は、文字列の最後に、拡張機能が添付されます。|  
|[CPathT::SkipRoot](#skiproot)|ドライブ文字または UNC サーバー/共有パスの一部を無視して、パスを解析するには、このメソッドを呼び出します。|  
|[CPathT::StripPath](#strippath)|完全修飾パスとファイル名のパス部分を削除するには、このメソッドを呼び出します。|  
|[CPathT::StripToRoot](#striptoroot)|ただし、ルート情報、パスのすべての部分を削除するには、このメソッドを呼び出します。|  
|[CPathT::UnquoteSpaces](#unquotespaces)|先頭と末尾のパスから引用符を削除するには、このメソッドを呼び出します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CPathT::operator const 文字列型 >/documents/report1.rdl」の](#operator_const_stringtype_amp)|この演算子は、文字列のように扱われ、オブジェクトを使用します。|  
|[CPathT::operator CPathT::PCXSTR](#operator_cpatht__pcxstr)|この演算子は、文字列のように扱われ、オブジェクトを使用します。|  
|[文字列型の CPathT::operator >/documents/report1.rdl」の](#operator_stringtype)|この演算子は、文字列のように扱われ、オブジェクトを使用します。|  
|[CPathT::operator + = 演算子](#operator_add_eq)|この演算子は、パスに文字列を追加します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CPathT::m_strPath](#m_strpath)|パス。|  
  
## <a name="remarks"></a>コメント  
 `CPath`、 `CPathA`、および`CPathW`のインスタンスを、`CPathT`次のように定義されています。  
  
 `typedef CPathT< CString > CPath;`  
  
 `typedef CPathT< CStringA > CPathA;`  
  
 `typedef CPathT< CStringW > CPathW;`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlpath.h  
  
##  <a name="a-nameaddbackslasha--cpathtaddbackslash"></a><a name="addbackslash"></a>CPathT::AddBackslash  
 パスの正しい構文を作成するための文字列の末尾に円記号を追加するには、このメソッドを呼び出します。 パスは、末尾に円記号を既に持っている場合は、円記号は追加されません。  
  
```
void AddBackslash();
```  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [PathAddBackSlash](http://msdn.microsoft.com/library/windows/desktop/bb773561)します。  
  
##  <a name="a-nameaddextensiona--cpathtaddextension"></a><a name="addextension"></a>CPathT::AddExtension  
 パスにファイル拡張子を追加するには、このメソッドを呼び出します。  
  
```
BOOL AddExtension(PCXSTR pszExtension);
```  
  
### <a name="parameters"></a>パラメーター  
 `pszExtension`  
 追加するファイル拡張子。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、TRUE を返しますを返します。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [PathAddExtension](http://msdn.microsoft.com/library/windows/desktop/bb773563)します。  
  
##  <a name="a-nameappenda--cpathtappend"></a><a name="append"></a>CPathT::Append  
 現在のパスに文字列を追加するには、このメソッドを呼び出します。  
  
```
BOOL Append(PCXSTR pszMore);
```  
  
### <a name="parameters"></a>パラメーター  
 `pszMore`  
 追加する文字列。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、TRUE を返しますを返します。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [PathAppend](http://msdn.microsoft.com/library/windows/desktop/bb773565)します。  
  
##  <a name="a-namebuildroota--cpathtbuildroot"></a><a name="buildroot"></a>CPathT::BuildRoot  
 特定のドライブ数からルートのパスを作成するには、このメソッドを呼び出します。  
  
```
void BuildRoot(int iDrive);
```  
  
### <a name="parameters"></a>パラメーター  
 *ドライブ*  
 ドライブの数 (0 は何ですか、1 は b: というように)。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [PathBuildRoot](http://msdn.microsoft.com/library/windows/desktop/bb773567)します。  
  
##  <a name="a-namecanonicalizea--cpathtcanonicalize"></a><a name="canonicalize"></a>CPathT::Canonicalize  
 パスを正規の形式に変換するには、このメソッドを呼び出します。  
  
```
void Canonicalize();
```  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [PathCanonicalize](http://msdn.microsoft.com/library/windows/desktop/bb773569)します。  
  
##  <a name="a-namecombinea--cpathtcombine"></a><a name="combine"></a>CPathT::Combine  
 ディレクトリ名を表す文字列とファイルのパス名を&1; つのパスを表す文字列を連結するには、このメソッドを呼び出します。  
  
```
void Combine(PCXSTR pszDir, PCXSTR  pszFile);
```  
  
### <a name="parameters"></a>パラメーター  
 `pszDir`  
 ディレクトリ パス。  
  
 *pszFile*  
 ファイルのパス。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [PathCombine](http://msdn.microsoft.com/library/windows/desktop/bb773571)します。  
  
##  <a name="a-namecommonprefixa--cpathtcommonprefix"></a><a name="commonprefix"></a>CPathT::CommonPrefix  
 指定されたパスが現在のパスと共通プレフィックスを共有するかどうかを判断するには、このメソッドを呼び出します。  
  
```
CPathT<StringType> CommonPrefix(PCXSTR pszOther);
```  
  
### <a name="parameters"></a>パラメーター  
 `pszOther`  
 現在のものと比較するパス。  
  
### <a name="return-value"></a>戻り値  
 共通のプレフィックスを返します。  
  
### <a name="remarks"></a>コメント  
 プレフィックスは、これらの型の&1; つです:"c:\\\\「,」です","..","..。\\\\". 詳細については、次を参照してください。 [PathCommonPrefix](http://msdn.microsoft.com/library/windows/desktop/bb773574)します。  
  
##  <a name="a-namecompactpatha--cpathtcompactpath"></a><a name="compactpath"></a>CPathT::CompactPath  
 省略記号をパス コンポーネントを置き換えることで、指定したピクセル幅に収まるようにファイル パスを短くには、このメソッドを呼び出します。  
  
```
BOOL CompactPath(HDC hDC, UINT nWidth);
```  
  
### <a name="parameters"></a>パラメーター  
 `hDC`  
 フォント メトリックに使用されるデバイス コンテキスト。  
  
 `nWidth`  
 幅 (ピクセル単位) に収まるように、文字列を強制されます。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、TRUE を返しますを返します。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [PathCompactPath](http://msdn.microsoft.com/library/windows/desktop/bb773575)します。  
  
##  <a name="a-namecompactpathexa--cpathtcompactpathex"></a><a name="compactpathex"></a>CPathT::CompactPathEx  
 省略記号をパス コンポーネントを置き換えることで、指定した文字数に収まるようにファイル パスを短くには、このメソッドを呼び出します。  
  
```
BOOL CompactPathEx(UINT nMaxChars, DWORD dwFlags = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 `nMaxChars`  
 終端の NULL 文字を含む、新しい文字列に含まれる文字の最大数。  
  
 `dwFlags`  
 予約済み。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、TRUE を返しますを返します。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [PathCompactPathEx](http://msdn.microsoft.com/library/windows/desktop/bb773578)します。  
  
##  <a name="a-namecpathta--cpathtcpatht"></a><a name="cpatht"></a>CPathT::CPathT  
 コンストラクターです。  
  
```
CPathT(PCXSTR pszPath);
CPathT(const CPathT<StringType>& path);
CPathT() throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *pszPath*  
 パス文字列へのポインター。  
  
 *path*  
 パス文字列。  
  
##  <a name="a-namefileexistsa--cpathtfileexists"></a><a name="fileexists"></a>CPathT::FileExists  
 このメソッドでは、このパス名でファイルが存在するかどうかを確認します。  
  
```
BOOL FileExists() const;
```  
  
### <a name="return-value"></a>戻り値  
 かどうか、ファイルが存在するそれ以外の場合は TRUE を返します。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [PathFileExists](http://msdn.microsoft.com/library/windows/desktop/bb773584)します。  
  
##  <a name="a-namefindextensiona--cpathtfindextension"></a><a name="findextension"></a>CPathT::FindExtension  
 パス内のファイル拡張子の位置を検索するには、このメソッドを呼び出します。  
  
```
int FindExtension() const;
```  
  
### <a name="return-value"></a>戻り値  
 位置を返します、"です。"前に、拡張機能です。 拡張機能が検出されない場合は、-1 を返します。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [PathFindExtension](http://msdn.microsoft.com/library/windows/desktop/bb773587)します。  
  
##  <a name="a-namefindfilenamea--cpathtfindfilename"></a><a name="findfilename"></a>CPathT::FindFileName  
 パス内のファイル名の位置を検索するには、このメソッドを呼び出します。  
  
```
int FindFileName() const;
```  
  
### <a name="return-value"></a>戻り値  
 ファイル名の位置を返します。 ファイル名が検出されない場合は、-1 を返します。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [PathFindFileName](http://msdn.microsoft.com/library/windows/desktop/bb773589)します。  
  
##  <a name="a-namegetdrivenumbera--cpathtgetdrivenumber"></a><a name="getdrivenumber"></a>CPathT::GetDriveNumber  
 このメソッドを呼び出して 'Z' を 'A' の範囲内のドライブ文字のパスを検索し、対応するドライブの数を返します。  
  
```
int GetDriveNumber() const;
```  
  
### <a name="return-value"></a>戻り値  
 パスにドライブ文字、または-1 それ以外の場合に 0 ~ 25 ('Z' を 'A' に対応する) を整数としてドライブの数を返します。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [PathGetDriveNumber](http://msdn.microsoft.com/library/windows/desktop/bb773612)します。  
  
##  <a name="a-namegetextensiona--cpathtgetextension"></a><a name="getextension"></a>CPathT::GetExtension  
 パスからファイルの拡張子を取得するには、このメソッドを呼び出します。  
  
```
StringType GetExtension() const;
```  
  
### <a name="return-value"></a>戻り値  
 ファイル拡張子を返します。  
  
##  <a name="a-nameisdirectorya--cpathtisdirectory"></a><a name="isdirectory"></a>CPathT::IsDirectory  
 パスが有効なディレクトリであるかどうかを確認するには、このメソッドを呼び出します。  
  
```
BOOL IsDirectory() const;
```  
  
### <a name="return-value"></a>戻り値  
 パスがディレクトリである場合、0 以外の値 (16) を返す`FALSE`それ以外の場合。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [PathIsDirectory](http://msdn.microsoft.com/library/windows/desktop/bb773621)します。  
  
##  <a name="a-nameisfilespeca--cpathtisfilespec"></a><a name="isfilespec"></a>CPathT::IsFileSpec  
 パス区切り文字のパスを検索するには、このメソッドを呼び出す (たとえば、':' または '\\')。 パス区切り文字がない場合、パスがファイルの仕様のパスと見なされます。  
  
```
BOOL IsFileSpec() const;
```  
  
### <a name="return-value"></a>戻り値  
 パス内に、パス区切り文字がない場合は TRUE またはパス区切り文字がある場合は FALSE を返します。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [PathIsFileSpec](http://msdn.microsoft.com/library/windows/desktop/bb773627)します。  
  
##  <a name="a-nameisprefixa--cpathtisprefix"></a><a name="isprefix"></a>CPathT::IsPrefix  
 パスにによって渡される種類の有効なプレフィックスが含まれるかどうか確認するには、このメソッドを呼び出す`pszPrefix`します。  
  
```
BOOL IsPrefix(PCXSTR pszPrefix) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `pszPrefix`  
 検索対象のプリフィックス。 プレフィックスは、これらの型の&1; つです:"c:\\\\「,」です","..","..。\\\\".  
  
### <a name="return-value"></a>戻り値  
 パスが含まれる場合、プレフィックス、または FALSE それ以外の場合は、TRUE を返します。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [PathIsPrefix](http://msdn.microsoft.com/library/windows/desktop/bb773650)します。  
  
##  <a name="a-nameisrelativea--cpathtisrelative"></a><a name="isrelative"></a>CPathT::IsRelative  
 このメソッドでは、パスが相対かを判断します。  
  
```
BOOL IsRelative() const;
```  
  
### <a name="return-value"></a>戻り値  
 絶対である場合、パスが相対パス、または FALSE の場合は TRUE を返します。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [PathIsRelative](http://msdn.microsoft.com/library/windows/desktop/bb773660)します。  
  
##  <a name="a-nameisroota--cpathtisroot"></a><a name="isroot"></a>CPathT::IsRoot  
 パスがディレクトリのルートであるかを判断するには、このメソッドを呼び出します。  
  
```
BOOL IsRoot() const;
```  
  
### <a name="return-value"></a>戻り値  
 パスは、ルートまたは FALSE をそれ以外の場合がある場合は、TRUE を返します。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [PathIsRoot](http://msdn.microsoft.com/library/windows/desktop/bb773674)します。  
  
##  <a name="a-nameissameroota--cpathtissameroot"></a><a name="issameroot"></a>CPathT::IsSameRoot  
 別のパスが現在のパスと、共通のルート コンポーネントを持つかどうかを判断するには、このメソッドを呼び出します。  
  
```
BOOL IsSameRoot(PCXSTR pszOther) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `pszOther`  
 別のパス。  
  
### <a name="return-value"></a>戻り値  
 両方の文字列には、それ以外の場合するルート コンポーネントが同じまたは FALSE がある場合は TRUE を返します。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [PathIsSameRoot](http://msdn.microsoft.com/library/windows/desktop/bb773687)します。  
  
##  <a name="a-nameisunca--cpathtisunc"></a><a name="isunc"></a>CPathT::IsUNC  
 パスが、サーバーの有効な UNC (汎用名前付け規則) パスであるかどうかを確認するには、このメソッドを呼び出すし、共有します。  
  
```
BOOL IsUNC() const;
```  
  
### <a name="return-value"></a>戻り値  
 パスは有効な UNC パスまたは FALSE をそれ以外の場合は TRUE を返します。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [PathIsUNC](http://msdn.microsoft.com/library/windows/desktop/bb773712)します。  
  
##  <a name="a-nameisuncservera--cpathtisuncserver"></a><a name="isuncserver"></a>CPathT::IsUNCServer  
 このメソッドでは、パスがサーバーだけを表す有効な UNC (汎用名前付け規則) パスであるかどうかを確認します。  
  
```
BOOL IsUNCServer() const;
```  
  
### <a name="return-value"></a>戻り値  
 文字列は、有効なサーバーのみの UNC パス (共有名がない)、または FALSE それ以外の場合は TRUE を返します。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [PathIsUNCServer](http://msdn.microsoft.com/library/windows/desktop/bb773722)します。  
  
##  <a name="a-nameisuncserversharea--cpathtisuncservershare"></a><a name="isuncservershare"></a>CPathT::IsUNCServerShare  
 パスが有効な UNC (汎用名前付け規則) 共有パスであるかどうかを確認するには、このメソッドを呼び出す\\ \  *server*\ *共有*します。  
  
```
BOOL IsUNCServerShare() const;
```  
  
### <a name="return-value"></a>戻り値  
 パスが、フォームの場合、TRUE を返します\\ \  *server*\ *共有*、FALSE またはそれ以外の場合。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [PathIsUNCServerShare](http://msdn.microsoft.com/library/windows/desktop/bb773723)します。  
  
##  <a name="a-namemstrpatha--cpathtmstrpath"></a><a name="m_strpath"></a>CPathT::m_strPath  
 パス。  
  
```
StringType m_strPath;
```  
  
### <a name="remarks"></a>コメント  
 `StringType`テンプレート パラメーターは、`CPathT`です。  
  
##  <a name="a-namemakeprettya--cpathtmakepretty"></a><a name="makepretty"></a>CPathT::MakePretty  
 パスをパスの外観を一貫性のある文字をすべて小文字に変換するには、このメソッドを呼び出します。  
  
```
BOOL MakePretty();
```  
  
### <a name="return-value"></a>戻り値  
 それ以外の場合、パスが変換された場合は TRUE または FALSE を返します。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [PathMakePretty](http://msdn.microsoft.com/library/windows/desktop/bb773725)します。  
  
##  <a name="a-namematchspeca--cpathtmatchspec"></a><a name="matchspec"></a>CPathT::MatchSpec  
 ワイルドカード一致の種類を含む文字列へのパスを検索するには、このメソッドを呼び出します。  
  
```
BOOL MatchSpec(PCXSTR pszSpec) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `pszSpec`  
 検索対象のファイルの種類と null で終わる文字列へのポインター。 たとえば、現在のパスにあるファイルが DOC ファイルであるかどうかをテストする`pszSpec`に設定する必要があります"* .doc"です。  
  
### <a name="return-value"></a>戻り値  
 それ以外の場合、文字列が一致する場合は TRUE または FALSE を返します。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [PathMatchSpec](http://msdn.microsoft.com/library/windows/desktop/bb773727)します。  
  
##  <a name="a-nameoperatoraddeqa--cpathtoperator-"></a><a name="operator_add_eq"></a>CPathT::operator + = 演算子  
 この演算子は、パスに文字列を追加します。  
  
```
CPathT<StringType>& operator+=(PCXSTR pszMore);
```  
  
### <a name="parameters"></a>パラメーター  
 `pszMore`  
 追加する文字列。  
  
### <a name="return-value"></a>戻り値  
 更新されたパスを返します。  
  
##  <a name="a-nameoperatorconststringtypeampa--cpathtoperator-const-stringtype-amp"></a><a name="operator_const_stringtype_amp"></a>CPathT::operator const 文字列型&amp;  
 この演算子は、文字列のように扱われ、オブジェクトを使用します。  
  
```
 operatorconst StringType&() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 このオブジェクトによって管理されている現在のパスを表す文字列を返します。  
  
##  <a name="a-nameoperatorcpathtpcxstra--cpathtoperator-cpathtpcxstr"></a><a name="operator_cpatht__pcxstr"></a>CPathT::operator CPathT::PCXSTR  
 この演算子は、文字列のように扱われ、オブジェクトを使用します。  
  
```
 operatorPCXSTR() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 このオブジェクトによって管理されている現在のパスを表す文字列を返します。  
  
##  <a name="a-nameoperatorstringtypeampa--cpathtoperator-stringtype-amp"></a><a name="operator_stringtype__amp"></a>CPathT::operator 文字列型&amp;  
 この演算子は、文字列のように扱われ、オブジェクトを使用します。  
  
```
 operatorStringType&() throw();
```  
  
### <a name="return-value"></a>戻り値  
 このオブジェクトによって管理されている現在のパスを表す文字列を返します。  
  
##  <a name="a-namepcxstra--cpathtpcxstr"></a><a name="pcxstr"></a>CPathT::PCXSTR  
 文字列定数の型。  
  
```
typedef StringType::PCXSTR PCXSTR;
```  
  
### <a name="remarks"></a>コメント  
 `StringType`テンプレート パラメーターは、`CPathT`です。  
  
##  <a name="a-namepxstra--cpathtpxstr"></a><a name="pxstr"></a>CPathT::PXSTR  
 文字列型です。  
  
```
typedef StringType::PXSTR PXSTR;
```  
  
### <a name="remarks"></a>コメント  
 `StringType`テンプレート パラメーターは、`CPathT`です。  
  
##  <a name="a-namequotespacesa--cpathtquotespaces"></a><a name="quotespaces"></a>CPathT::QuoteSpaces  
 このメソッドを呼び出して、スペースが含まれている場合は、パスを引用符で囲みます。  
  
```
void QuoteSpaces();
```  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [PathQuoteSpaces](http://msdn.microsoft.com/library/windows/desktop/bb773739)します。  
  
##  <a name="a-namerelativepathtoa--cpathtrelativepathto"></a><a name="relativepathto"></a>CPathT::RelativePathTo  
 1 つのファイルまたはフォルダーから別の相対パスを作成するには、このメソッドを呼び出します。  
  
```
BOOL RelativePathTo(
    PCXSTR pszFrom,
    DWORD dwAttrFrom,
    PCXSTR pszTo,
    DWORD dwAttrTo);
```  
  
### <a name="parameters"></a>パラメーター  
 `pszFrom`  
 相対パスの開始時刻です。  
  
 *dwAttrFrom*  
 ファイル属性の`pszFrom`です。 この値には、FILE_ATTRIBUTE_DIRECTORY が含まれている場合`pszFrom`ディレクトリにすることが想定されない場合は、`pszFrom`ファイルであると見なされます。  
  
 `pszTo`  
 相対パスの終点です。  
  
 *dwAttrTo*  
 ファイル属性の`pszTo`です。 この値には、FILE_ATTRIBUTE_DIRECTORY が含まれている場合`pszTo`ディレクトリにすることが想定されない場合は、`pszTo`ファイルであると見なされます。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、TRUE を返しますを返します。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [PathRelativePathTo](http://msdn.microsoft.com/library/windows/desktop/bb773740)します。  
  
##  <a name="a-nameremoveargsa--cpathtremoveargs"></a><a name="removeargs"></a>CPathT::RemoveArgs  
 パスから、コマンドライン引数を削除するには、このメソッドを呼び出します。  
  
```
void RemoveArgs();
```  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [PathRemoveArgs](http://msdn.microsoft.com/library/windows/desktop/bb773742)します。  
  
##  <a name="a-nameremovebackslasha--cpathtremovebackslash"></a><a name="removebackslash"></a>CPathT::RemoveBackslash  
 パスから、末尾に円記号を削除するには、このメソッドを呼び出します。  
  
```
void RemoveBackslash();
```  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [PathRemoveBackslash](http://msdn.microsoft.com/library/windows/desktop/bb773743)します。  
  
##  <a name="a-nameremoveblanksa--cpathtremoveblanks"></a><a name="removeblanks"></a>CPathT::RemoveBlanks  
 パスのすべての先頭および末尾のスペースを削除するには、このメソッドを呼び出します。  
  
```
void RemoveBlanks();
```  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [PathRemoveBlanks](http://msdn.microsoft.com/library/windows/desktop/bb773745)します。  
  
##  <a name="a-nameremoveextensiona--cpathtremoveextension"></a><a name="removeextension"></a>CPathT::RemoveExtension  
 1 つを使用する必要がある場合は、パスからファイルの拡張子を削除するには、このメソッドを呼び出します。  
  
```
void RemoveExtension();
```  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [PathRemoveExtension](http://msdn.microsoft.com/library/windows/desktop/bb773746)します。  
  
##  <a name="a-nameremovefilespeca--cpathtremovefilespec"></a><a name="removefilespec"></a>CPathT::RemoveFileSpec  
 それらがある場合は、パスの末尾にファイル名と円記号を削除するには、このメソッドを呼び出します。  
  
```
BOOL RemoveFileSpec();
```  
  
### <a name="return-value"></a>戻り値  
 成功した場合、TRUE を返しますを返します。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [PathRemoveFileSpec](http://msdn.microsoft.com/library/windows/desktop/bb773748)します。  
  
##  <a name="a-namerenameextensiona--cpathtrenameextension"></a><a name="renameextension"></a>CPathT::RenameExtension  
 このメソッドを呼び出して、新しい拡張機能で、パスにファイル名拡張子を置き換えます。 ファイル名に拡張子が含まれていない場合は、パスの末尾に拡張子が添付されます。  
  
```
BOOL RenameExtension(PCXSTR pszExtension);
```  
  
### <a name="parameters"></a>パラメーター  
 `pszExtension`  
 ファイル名の新しい拡張子を"です。"文字です。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、TRUE を返しますを返します。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [PathRenameExtension](http://msdn.microsoft.com/library/windows/desktop/bb773749)します。  
  
##  <a name="a-nameskiproota--cpathtskiproot"></a><a name="skiproot"></a>CPathT::SkipRoot  
 ドライブ文字または UNC (汎用名前付け規則) サーバー/共有パスの一部を無視して、パスを解析するには、このメソッドを呼び出します。  
  
```
int SkipRoot() const;
```  
  
### <a name="return-value"></a>戻り値  
 (ドライブ文字または UNC サーバー/共有) のルートに続くサブパスの先頭の位置を返します。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [PathSkipRoot](http://msdn.microsoft.com/library/windows/desktop/bb773754)します。  
  
##  <a name="a-namestrippatha--cpathtstrippath"></a><a name="strippath"></a>CPathT::StripPath  
 完全修飾パスとファイル名のパス部分を削除するには、このメソッドを呼び出します。  
  
```
void StripPath();
```  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [PathStripPath](http://msdn.microsoft.com/library/windows/desktop/bb773756)します。  
  
##  <a name="a-namestriptoroota--cpathtstriptoroot"></a><a name="striptoroot"></a>CPathT::StripToRoot  
 ただし、ルート情報、パスのすべての部分を削除するには、このメソッドを呼び出します。  
  
```
BOOL StripToRoot();
```  
  
### <a name="return-value"></a>戻り値  
 有効なドライブ文字の場合は TRUE を返します。 は、それ以外の場合 FALSE またはそれ、パスで検出されました。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [PathStripToRoot](http://msdn.microsoft.com/library/windows/desktop/bb773757)します。  
  
##  <a name="a-nameunquotespacesa--cpathtunquotespaces"></a><a name="unquotespaces"></a>CPathT::UnquoteSpaces  
 先頭と末尾のパスから引用符を削除するには、このメソッドを呼び出します。  
  
```
void UnquoteSpaces();
```  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [PathUnquoteSpaces](http://msdn.microsoft.com/library/windows/desktop/bb773763)します。  
  
##  <a name="a-namexchara--cpathtxchar"></a><a name="xchar"></a>CPathT::XCHAR  
 文字型です。  
  
```
typedef StringType::XCHAR XCHAR;
```  
  
### <a name="remarks"></a>コメント  
 `StringType`テンプレート パラメーターは、`CPathT`です。  
  
## <a name="see-also"></a>関連項目  
 [クラス](../../atl/reference/atl-classes.md)   
 [CStringT クラス](../../atl-mfc-shared/reference/cstringt-class.md)
