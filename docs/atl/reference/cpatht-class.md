---
title: "CPathT クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CPathT"
  - "CPathT"
  - "ATL::CPathT<StringType>"
  - "ATL::CPathT"
  - "ATL.CPathT<StringType>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CPathT クラス"
ms.assetid: eba4137d-1fd2-4b44-a2e1-0944db64df3c
caps.latest.revision: 20
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CPathT クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスはパスを表します。  
  
> [!IMPORTANT]
>  このクラスおよびメンバーは、Windows のランタイムで実行するアプリケーションで使用することはできません。  
  
## 構文  
  
```  
  
      template< typename   
      StringType  
      >   
class CPathT  
```  
  
#### パラメーター  
 `StringType`  
 パスで使用する ATL\/MFC の文字列クラス \( [CStringT](../../atl-mfc-shared/reference/cstringt-class.md)を参照\)。  
  
## メンバー  
  
### パブリック typedef  
  
|名前|説明|  
|--------|--------|  
|[CPathT::PCXSTR](../Topic/CPathT::PCXSTR.md)|文字列定数の型。|  
|[CPathT::PXSTR](../Topic/CPathT::PXSTR.md)|文字列型。|  
|[CPathT::XCHAR](../Topic/CPathT::XCHAR.md)|文字型です。|  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CPathT::CPathT](../Topic/CPathT::CPathT.md)|パスのコンストラクター。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CPathT::AddBackslash](../Topic/CPathT::AddBackslash.md)|文字列の末尾に円記号をパスの正しい構文を作成するために追加のためにこのメソッドを呼び出します。|  
|[CPathT::AddExtension](../Topic/CPathT::AddExtension.md)|パスにファイル拡張子を追加するには、このメソッドを呼び出します。|  
|[CPathT::Append](../Topic/CPathT::Append.md)|現在のパスに文字列を追加するには、このメソッドを呼び出します。|  
|[CPathT::BuildRoot](../Topic/CPathT::BuildRoot.md)|特定のドライブ番号のルート パスを作成するには、このメソッドを呼び出します。|  
|[CPathT::Canonicalize](../Topic/CPathT::Canonicalize.md)|正規形式のパスを変換するには、このメソッドを呼び出します。|  
|[CPathT::Combine](../Topic/CPathT::Combine.md)|ディレクトリ名を表す文字列と 1 個のパスにファイルのパス名を表す文字列を連結するには、このメソッドを呼び出します。|  
|[CPathT::CommonPrefix](../Topic/CPathT::CommonPrefix.md)|指定したパスが現在のパスで同じプレフィックスを持つかどうかを判定するためにこのメソッドを呼び出します。|  
|[CPathT::CompactPath](../Topic/CPathT::CompactPath.md)|ファイルのパスを楕円とパスのコンポーネントを置き換えることで、特定のピクセル幅に合わせてに省略するようにこのメソッドを呼び出します。|  
|[CPathT::CompactPathEx](../Topic/CPathT::CompactPathEx.md)|ファイルのパスを楕円とパスのコンポーネントを置き換えることで、特定の文字の番号内に収まるように省略するようにこのメソッドを呼び出します。|  
|[CPathT::FileExists](../Topic/CPathT::FileExists.md)|このパス名のファイルが存在するかどうかを確認するには、このメソッドを呼び出します。|  
|[CPathT::FindExtension](../Topic/CPathT::FindExtension.md)|パス内のファイル拡張子の位置を検索するには、このメソッドを呼び出します。|  
|[CPathT::FindFileName](../Topic/CPathT::FindFileName.md)|パス内のファイル名の位置を検索するには、このメソッドを呼び出します。|  
|[CPathT::GetDriveNumber](../Topic/CPathT::GetDriveNumber.md)|パスを Z "を" A のスコープ内のドライブ文字を検索し、対応するドライブ番号を返すには、このメソッドを呼び出します。|  
|[CPathT::GetExtension](../Topic/CPathT::GetExtension.md)|パスからファイル拡張子を取得するときにこのメソッドを呼び出します。|  
|[CPathT::IsDirectory](../Topic/CPathT::IsDirectory.md)|パスが有効なディレクトリかどうかを調べます。|  
|[CPathT::IsFileSpec](../Topic/CPathT::IsFileSpec.md)|パス区切り文字をパスを検索するには、このメソッドを呼び出します \(たとえば、「: "または「\\」\)。  現在のパス区切り文字がない場合は、ファイル パスの指定のパスと見なされます。|  
|[CPathT::IsPrefix](../Topic/CPathT::IsPrefix.md)|パスが `pszPrefix`を渡された型の有効なプレフィックスが含まれているかどうかを判定するためにこのメソッドを呼び出します。|  
|[CPathT::IsRelative](../Topic/CPathT::IsRelative.md)|パスは、相対パスであるかどうかを判定するためにこのメソッドを呼び出します。|  
|[CPathT::IsRoot](../Topic/CPathT::IsRoot.md)|パスがディレクトリのルートにあるかどうかを判定するためにこのメソッドを呼び出します。|  
|[CPathT::IsSameRoot](../Topic/CPathT::IsSameRoot.md)|別のパスが現在のパスを持つクラスをコンポーネントがあるかどうかを判定するためにこのメソッドを呼び出します。|  
|[CPathT::IsUNC](../Topic/CPathT::IsUNC.md)|パスがサーバーと共有の有効な UNC \(Universal 名前付け規則\) のパスであるかどうかを判定するためにこのメソッドを呼び出します。|  
|[CPathT::IsUNCServer](../Topic/CPathT::IsUNCServer.md)|パスがサーバーに対してのみ有効な UNC \(Universal 名前付け規則\) のパスであるかどうかを判定するためにこのメソッドを呼び出します。|  
|[CPathT::IsUNCServerShare](../Topic/CPathT::IsUNCServerShare.md)|\(\\\\*server*\\*share*パスが有効な UNC \(Universal 名前付け規則\) の共有パスであるかどうかを判定するためにこのメソッドを呼び出します。|  
|[CPathT::MakePretty](../Topic/CPathT::MakePretty.md)|小文字にパスをパスに一貫した外観を与えるために変換するためにこのメソッドを呼び出します。|  
|[CPathT::MatchSpec](../Topic/CPathT::MatchSpec.md)|ワイルドカードの型を含む文字列をパスを検索するには、このメソッドを呼び出します。|  
|[CPathT::QuoteSpaces](../Topic/CPathT::QuoteSpaces.md)|空白が含まれる場合は、パスを引用符で囲むようにこのメソッドを呼び出します。|  
|[CPathT::RelativePathTo](../Topic/CPathT::RelativePathTo.md)|1 個のファイルまたはフォルダーから他の状態への相対パスを作成するには、このメソッドを呼び出します。|  
|[CPathT::RemoveArgs](../Topic/CPathT::RemoveArgs.md)|パスからコマンド ライン引数を削除するには、このメソッドを呼び出します。|  
|[CPathT::RemoveBackslash](../Topic/CPathT::RemoveBackslash.md)|パスの末尾に円記号を削除するには、このメソッドを呼び出します。|  
|[CPathT::RemoveBlanks](../Topic/CPathT::RemoveBlanks.md)|パスの先頭と末尾の空白を削除するには、このメソッドを呼び出します。|  
|[CPathT::RemoveExtension](../Topic/CPathT::RemoveExtension.md)|が 1 の場合、パスからファイル拡張子を削除するには、このメソッドを呼び出します。|  
|[CPathT::RemoveFileSpec](../Topic/CPathT::RemoveFileSpec.md)|それらがある場合は、ファイル名とパスの末尾に円記号を削除するには、このメソッドを呼び出します。|  
|[CPathT::RenameExtension](../Topic/CPathT::RenameExtension.md)|新しい拡張子とパスのファイル名拡張子を置き換えるためにこのメソッドを呼び出します。  ファイル名の拡張子が含まれていない場合、拡張機能は、文字列の末尾にアタッチされます。|  
|[CPathT::SkipRoot](../Topic/CPathT::SkipRoot.md)|パスを解析するには、このメソッドを呼び出します。ドライブ文字または UNC 共有\/サーバー パスの一部を無視します。|  
|[CPathT::StripPath](../Topic/CPathT::StripPath.md)|絶対パスとファイル名のパス部分を削除するには、このメソッドを呼び出します。|  
|[CPathT::StripToRoot](../Topic/CPathT::StripToRoot.md)|ルートの情報を除きパスのすべての部分を削除するには、このメソッドを呼び出します。|  
|[CPathT::UnquoteSpaces](../Topic/CPathT::UnquoteSpaces.md)|引用符およびパスの末尾を最初から削除するには、このメソッドを呼び出します。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[CPathT::operator const StringType &](../Topic/CPathT::operator%20const%20StringType%20&.md)|この演算子は、オブジェクトが文字列と同様に処理されるようにします。|  
|[CPathT::operator CPathT::PCXSTR](../Topic/CPathT::operator%20CPathT::PCXSTR.md)|この演算子は、オブジェクトが文字列と同様に処理されるようにします。|  
|[CPathT::operator StringType &](../Topic/CPathT::operator%20StringType%20&.md)|この演算子は、オブジェクトが文字列と同様に処理されるようにします。|  
|[CPathT::operator \+\=](../Topic/CPathT::operator%20+=.md)|この演算子は、パスに文字列を追加します。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CPathT::m\_strPath](../Topic/CPathT::m_strPath.md)|パス。|  
  
## 解説  
 次のように`CPath`、`CPathA`と `CPathW` はインスタンス化 `CPathT` の定義です:  
  
 `typedef CPathT< CString > CPath;`  
  
 `typedef CPathT< CStringA > CPathA;`  
  
 `typedef CPathT< CStringW > CPathW;`  
  
## 必要条件  
 **Header:** atlpath.h  
  
## 参照  
 [クラス](../../atl/reference/atl-classes.md)   
 [CStringT クラス](../../atl-mfc-shared/reference/cstringt-class.md)