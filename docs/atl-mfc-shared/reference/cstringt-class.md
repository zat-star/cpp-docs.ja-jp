---
title: "CStringT クラス | Microsoft Docs"
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
  - "CString"
  - "CStringT"
  - "ATL::CStringT"
  - "ATL.CStringT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CStringT クラス"
  - "共有クラス, CStringT"
  - "文字列 [C++], ATL で"
ms.assetid: 7cacc59c-425f-40f1-8f5b-6db921318ec9
caps.latest.revision: 33
caps.handback.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CStringT クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスは、`CStringT` オブジェクトを表します。  
  
## 構文  
  
```  
  
      template< typename   
      BaseType  
      , class   
      StringTraits  
       >  
class CStringT :   
public CSimpleStringT<   BaseType,   _CSTRING_IMPL_::_MFCDLLTraitsCheck<      BaseType,      StringTraits   >   ::c_bIsMFCDLLTraits>  
```  
  
#### パラメーター  
 `BaseType`  
 文字列クラスの文字型。  次のいずれかになります。  
  
-   `char` \(ANSI 文字列の場合\)。  
  
-   `wchar_t` \(Unicode 文字列の場合\)。  
  
-   **TCHAR** \(ANSI 文字列と Unicode 文字列の両方の場合\)。  
  
 `StringTraits`  
 文字列クラスが C ランタイム \(CRT: C Run\-Time\) ライブラリのサポートを必要とするかどうか、および文字列リソースが置かれている場所を決定する値。  次のいずれかになります。  
  
-   **StrTraitATL\< wchar\_t** &#124; `char` &#124; **TCHAR, ChTraitsCRT\< wchar\_t** &#124; `char` &#124; **TCHAR \> \>**  
  
     クラスは CRT のサポートを必要とし、`m_hInstResource` \(アプリケーションのモジュール クラスのメンバー\) によって指定されたモジュールでリソース文字列を検索します。  
  
-   **StrTraitATL\< wchar\_t** &#124; `char` &#124; **TCHAR, ChTraitsOS\< wchar\_t** &#124; `char` &#124; **TCHAR \> \>**  
  
     クラスは CRT のサポートを必要とせず、`m_hInstResource` \(アプリケーションのモジュール クラスのメンバー\) によって指定されたモジュールでリソース文字列を検索します。  
  
-   **StrTraitMFC\< wchar\_t** &#124; `char` &#124; **TCHAR, ChTraitsCRT\< wchar\_t** &#124; `char` &#124; **TCHAR \> \>**  
  
     クラスは CRT のサポートを必要とし、標準の MFC 検索アルゴリズムを使用してリソース文字列を検索します。  
  
-   **StrTraitMFC\< wchar\_t** &#124; `char` &#124; **TCHAR, ChTraitsOS\< wchar\_t** &#124; `char` &#124; **TCHAR \> \>**  
  
     クラスは CRT のサポートを必要とせず、標準の MFC 検索アルゴリズムを使用してリソース文字列を検索します。  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CStringT::CStringT](../Topic/CStringT::CStringT.md)|さまざまな方法で `CStringT` オブジェクトを構築します。|  
|[CStringT::~CStringT](../Topic/CStringT::~CStringT.md)|`CStringT` オブジェクトを破棄します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CStringT::AllocSysString](../Topic/CStringT::AllocSysString.md)|`CStringT` データから `BSTR` を割り当てます。|  
|[CStringT::AnsiToOem](../Topic/CStringT::AnsiToOem.md)|ANSI 文字セットから OEM 文字セットに埋め込み先で変換します。|  
|[CStringT::AppendFormat](../Topic/CStringT::AppendFormat.md)|書式付きデータを既存の `CStringT` オブジェクトに付け加えます。|  
|[CStringT::Collate](../Topic/CStringT::Collate.md)|ロケール固有の情報に基づき、2 つの文字列を比較します。大文字と小文字を区別します。|  
|[CStringT::CollateNoCase](../Topic/CStringT::CollateNoCase.md)|ロケール固有の情報に基づき、2 つの文字列を比較します。大文字と小文字を区別しません。|  
|[CStringT::Compare](../Topic/CStringT::Compare.md)|大文字と小文字を区別して 2 つの文字列を比較します。|  
|[CStringT::CompareNoCase](../Topic/CStringT::CompareNoCase.md)|大文字と小文字を区別せずに 2 つの文字列を比較します。|  
|[CStringT::Delete](../Topic/CStringT::Delete.md)|文字列から 1 文字または複数の文字を削除します。|  
|[CStringT::Find](../Topic/CStringT::Find.md)|文字列内の文字または部分文字列を検索します。|  
|[CStringT::FindOneOf](../Topic/CStringT::FindOneOf.md)|文字セットで最初に一致する文字を検索します。|  
|[CStringT::Format](../Topic/CStringT::Format.md)|`sprintf` と同じように文字列を書式化します。|  
|[CStringT::FormatMessage](../Topic/CStringT::FormatMessage.md)|メッセージ文字列を書式化します。|  
|[CStringT::FormatMessageV](../Topic/CStringT::FormatMessageV.md)|可変個引数リストを使用してメッセージ文字列を書式化します。|  
|[CStringT::FormatV](../Topic/CStringT::FormatV.md)|可変個の引数のリストを使用して文字列を書式化します。|  
|[CStringT::GetEnvironmentVariable](../Topic/CStringT::GetEnvironmentVariable.md)|文字列を指定された環境変数の値に設定します。|  
|[CStringT::Insert](../Topic/CStringT::Insert.md)|文字列内の指定されたインデックス位置に 1 文字または部分文字列を挿入します。|  
|[CStringT::Left](../Topic/CStringT::Left.md)|文字列の左の部分を抽出します。|  
|[CStringT::LoadString](../Topic/CStringT::LoadString.md)|Windows のリソースから既存の `CStringT` オブジェクトを読み込みます。|  
|[CStringT::MakeLower](../Topic/CStringT::MakeLower.md)|文字列内のすべての文字を小文字に変換します。|  
|[CStringT::MakeReverse](../Topic/CStringT::MakeReverse.md)|文字列を反転します。|  
|[CStringT::MakeUpper](../Topic/CStringT::MakeUpper.md)|文字列内のすべての文字を大文字に変換します。|  
|[CStringT::Mid](../Topic/CStringT::Mid.md)|文字列の中央の部分を抽出します。|  
|[CStringT::OemToAnsi](../Topic/CStringT::OemToAnsi.md)|OEM 文字セットから ANSI 文字セットに埋め込み先で変換します。|  
|[CStringT::Remove](../Topic/CStringT::Remove.md)|指定された文字を文字列から削除します。|  
|[CStringT::Replace](../Topic/CStringT::Replace.md)|指定された文字をほかの文字に置き換えます。|  
|[CStringT::ReverseFind](../Topic/CStringT::ReverseFind.md)|文字列内の文字を検索します。文字列の末尾から先頭方向へ検索します。|  
|[CStringT::Right](../Topic/CStringT::Right.md)|文字列の右の部分を抽出します。|  
|[CStringT::SetSysString](../Topic/CStringT::SetSysString.md)|データを持つ既存の `BSTR` オブジェクトを `CStringT` オブジェクトから設定します。|  
|[CStringT::SpanExcluding](../Topic/CStringT::SpanExcluding.md)|文字列の最初の文字から始まり `pszCharSet` にない文字が出現するまでの部分文字列を抽出します。|  
|[CStringT::SpanIncluding](../Topic/CStringT::SpanIncluding.md)|指定した文字セットの文字だけで構成されている部分文字列を抽出します。|  
|[CStringT::Tokenize](../Topic/CStringT::Tokenize.md)|対象の文字列内の指定されたトークンを抽出します。|  
|[CStringT::Trim](../Topic/CStringT::Trim.md)|文字列の先頭と末尾にある空白文字を取り除きます。|  
|[CStringT::TrimLeft](../Topic/CStringT::TrimLeft.md)|文字列の先頭にある空白文字を取り除きます。|  
|[CStringT::TrimRight](../Topic/CStringT::TrimRight.md)|文字列の末尾にある空白文字を取り除きます。|  
  
### 演算子  
  
|||  
|-|-|  
|[CStringT::operator \=](../Topic/CStringT::operator%20=.md)|`CStringT` オブジェクトに新しい値を代入します。|  
|[CStringT::operator \+](../Topic/CStringT::operator%20+.md)|2 つの文字列、または 1 文字と 1 つの文字列を連結します。|  
|[CStringT::operator \+\=](../Topic/CStringT::operator%20+=.md)|既存の文字列の末尾に新しい文字列を連結します。|  
|[CStringT::operator \=\=](../Topic/CStringT::operator%20==.md)|2 つの文字列が論理的に等しいかどうかを判断します。|  
|[CStringT::operator \!\=](../Topic/CStringT::operator%20!=.md)|2 つの文字列が論理的に等しくないかどうかを判断します。|  
|[CStringT::operator \<](../Topic/CStringT::operator%20%3C.md)|演算子の左側の文字列が右側の文字列より小さいかどうかを判断します。|  
|[CStringT::operator \>](../Topic/CStringT::operator%20%3E.md)|演算子の左側の文字列が右側の文字列より大きいかどうかを判断します。|  
|[CStringT::operator \<\=](../Topic/CStringT::operator%20%3C=.md)|演算子の左側の文字列が右側の文字列以下かどうかを判断します。|  
|[CStringT::operator \>\=](../Topic/CStringT::operator%20%3E=.md)|演算子の左側の文字列が右側の文字列以上かどうかを判断します。|  
  
## 解説  
 `CStringT` は [CSimpleStringT クラス](../../atl-mfc-shared/reference/csimplestringt-class.md)を継承します。  文字の操作、順序付け、検索などの拡張機能は `CStringT` によって実装されます。  
  
> [!NOTE]
>  `CStringT` オブジェクトには例外をスローする機能があります。  なんらかの理由により `CStringT` オブジェクトがメモリ不足になると、例外がスローされます。  
  
 `CStringT` オブジェクトは、可変長の文字列から構成されます。  `CStringT` には、Basic に似た構文を使用する関数と演算子が用意されています。  簡易化されたメモリ管理と合わせて、連結演算子や比較演算子により、通常の文字配列よりも `CStringT` オブジェクトの方が扱いやすくなっています。  
  
> [!NOTE]
>  null 文字を埋め込んだ `CStringT` インスタンスを作成することは可能ですが、お勧めはしません。  null 文字が埋め込まれた `CStringT` オブジェクトに対してメソッドまたは演算子を呼び出すと、予期しない結果が生じることがあります。  
  
 `BaseType` のパラメーターと `StringTraits` のパラメーターをさまざまに組み合わせることにより、`CStringT` オブジェクトは以下のような型になります。これらの型は、ATL ライブラリによって定義済みです。  
  
 ATL アプリケーションを使用する場合  
  
 `CString`、`CStringA`、および `CStringW` は、ユーザーの DLL からではなく、MFC DLL \(MFC90.DLL\) からエクスポートされます。  これは `CStringT` の多重定義を防止するためです。  
  
> [!NOTE]
>  `CString`\- Visual C\+\+ .NET 2002 の MFC 拡張 DLL の派生クラス エクスポートするときに適用し、サポート技術情報の文書"に説明されているように、代替手段をリンカーのエラーが、これは Visual C\+\+ .NET 2003 で、修正済み CString 派生クラス」をインポートするときにエラー リンク Q309801 回避策コードを削除する必要があります。  サポート技術情報の文書は、MSDN ライブラリ CD\-ROM または [http:\/\/support.microsoft.com\/default.aspx](http://support.microsoft.com/default.aspx) で参照できます。  
  
 MFC ベースのアプリケーション内では、次の文字列型を使用できます。  
  
|CStringT 型|宣言|  
|----------------|--------|  
|`CStringA`|CRT サポート機能を持つ ANSI 文字型の文字列。|  
|`CStringW`|CRT サポート機能を持つ Unicode 文字型の文字列。|  
|`CString`|CRT サポート機能を持つ ANSI 文字型と Unicode 文字型の両方。|  
  
 **ATL\_CSTRING\_NO\_CRT** が定義されているプロジェクトでは、次の文字列型を使用できます。  
  
|CStringT 型|宣言|  
|----------------|--------|  
|**CAtlStringA**|CRT サポート機能のない ANSI 文字型の文字列。|  
|**CAtlStringW**|CRT サポート機能のない Unicode 文字型の文字列。|  
|**CAtlString**|CRT サポート機能のない ANSI 文字型と Unicode 文字型の両方。|  
  
 **ATL\_CSTRING\_NO\_CRT** が定義されていないプロジェクトでは、次の文字列型を使用できます。  
  
|CStringT 型|宣言|  
|----------------|--------|  
|**CAtlStringA**|CRT サポート機能を持つ ANSI 文字型の文字列。|  
|**CAtlStringW**|CRT サポート機能を持つ Unicode 文字型の文字列。|  
|**CAtlString**|CRT サポート機能を持つ ANSI 文字型と Unicode 文字型の両方。|  
  
 また、`CString` オブジェクトは次の特性を持っています。  
  
-   `CStringT` オブジェクトは、連結操作で拡張できます。  
  
-   `CStringT` オブジェクトは値に基づいて操作が決定されます。`CStringT` オブジェクトは文字列へのポインターとしてではなく、実際の文字列として考えてください。  
  
-   関数の引数 `PCXSTR` の代わりに自由に `CStringT` を使用できます。  
  
-   文字列バッファーに対してカスタムのメモリ管理を実装できます。  詳細については、「[メモリ管理と CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md)」を参照してください。  
  
## CStringT 定義済みの型  
 `CStringT` は、テンプレートの引数を使用してサポートされる文字型 \([wchar\_t](../../c-runtime-library/standard-types.md) または [char](../../c-runtime-library/standard-types.md)\) を定義するため、場合によってはメソッドのパラメーターの型が複雑になることがあります。  このように型が複雑化するのを避けるため、一連の定義済みの型が定義されており、`CStringT` クラス全体で使用されます。  型の一覧を次に示します。  
  
|名前|説明|  
|--------|--------|  
|`XCHAR`|`CStringT` オブジェクトと同じ文字型の 1 文字 \(`wchar_t` または `char` のいずれか\)。|  
|**YCHAR**|`CStringT` オブジェクトと異なる文字型の 1 文字 \(`wchar_t` または `char` のいずれか\)。|  
|`PXSTR`|`CStringT` オブジェクトと同じ文字型の文字列 \(`wchar_t` または `char` のいずれか\) へのポインター。|  
|**PYSTR**|`CStringT` オブジェクトと異なる文字型の文字列 \(`wchar_t` または `char` のいずれか\) へのポインター。|  
|`PCXSTR`|`CStringT` オブジェクトと同じ文字型の **const** 文字列 \(`wchar_t` または `char` のいずれか\) へのポインター。|  
|**PCYSTR**|`CStringT` オブジェクトと異なる文字型の **const** 文字列 \(`wchar_t` または `char` のいずれか\) へのポインター。|  
  
> [!NOTE]
>  `CString` の非公開のメソッド \(**AssignCopy** など\) を使用したコードは、`CStringT` の公開メソッド \(`GetBuffer` や `ReleaseBuffer` など\) を使用するコードで置換する必要があります。  これらのメソッドは `CSimpleStringT`から継承されます。  
  
## 継承階層  
 [CSimpleStringT](../../atl-mfc-shared/reference/csimplestringt-class.md)  
  
 `CStringT`  
  
## 必要条件  
  
|Header|用途|  
|------------|--------|  
|cstringt.h|MFC 専用文字列オブジェクト|  
|atlstr.h|非 MFC 文字列オブジェクト|  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [ATL\/MFC の共有クラス](../../atl-mfc-shared/atl-mfc-shared-classes.md)   
 [CSimpleStringT クラス](../../atl-mfc-shared/reference/csimplestringt-class.md)