---
title: "CString 引数の渡し方 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "引数渡し [C++]"
  - "引数渡し [C++], C の文字列"
  - "引数 [C++], 渡す"
  - "CString オブジェクト, 渡す (引数を)"
  - "関数 [C++], 文字列 (入出力として)"
  - "渡す (引数を), C の文字列"
  - "string 引数"
  - "文字列 [C++], 関数の入出力としての"
ms.assetid: a67bebff-edf1-4cf4-bbff-d1cc6a901099
caps.latest.revision: 13
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CString 引数の渡し方
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ここでは [CString](../atl-mfc-shared/reference/cstringt-class.md) オブジェクトを関数の引数や戻り値として利用する方法について説明します。`CString`  
  
##  <a name="_core_cstring_argument.2d.passing_conventions"></a> CString の引数渡し規約  
 クラスのインターフェイスを定義するときは、メンバー関数の引数渡し規約を決める必要があります。  `CString` オブジェクトを関数の引数または戻り値として使用する場合はいくつかの標準的な規則があります。  これらの規則 \(「[関数入力として文字列を利用する場合](#_core_strings_as_function_inputs)」と「[関数出力として文字列を利用する場合](#_core_strings_as_function_outputs)」を参照\) に従うと、コードが効率的で正確になります。  
  
##  <a name="_core_strings_as_function_inputs"></a> 関数入力として文字列を利用する場合  
 呼び出される関数の中で `CString` オブジェクトを最も効率的かつ安全に使用する方法は、関数に `CString` オブジェクトを渡すことです。  名前に反して、`CString` オブジェクトは、null 終端文字がある C スタイルの文字列として文字列を内部的に格納しません。  代わりに、`CString` オブジェクトは、文字列の文字数を追跡します。  `CString` を使用して null で終わる文字列への `LPCTSTR` ポインターを設定することは小さな操作ですが、コード内でその操作を常に実行する必要がある場合はたいへんな作業になる可能性があります。  `CString` の内容を変更すると `LPCTSTR` ポインターの古いコピーが無効になるので、結果は一時的なものです。  
  
 C スタイルの文字列を指定することに意味がある場合があります。  たとえば、呼び出される関数が C で記述され、オブジェクトをサポートしていない状況が考えられます。  この場合は、`CString` パラメーターを `LPCTSTR` に強制的に変換すると、関数で C スタイルの null で終わる文字列が取得されます。  さらに、C スタイルの文字列パラメーターを指定できる `CString` コンストラクターを使用して `CString` オブジェクトを作成する方法もあります。  
  
 関数の中で文字列の値を変更する場合は、パラメーターとして非定数 `CString` 型への参照 \(**CString&**\) を宣言します。  
  
##  <a name="_core_strings_as_function_outputs"></a> 関数出力として文字列を利用する場合  
 通常は、`CString` オブジェクトはプリミティブ型同様の値セマンティクスに従うため、関数から `CString` オブジェクトを返すことができます。  読み取り専用文字列を戻り値にするときは、定数 `CString` 型への参照 \(**const CString&**\) として宣言します。  次の例では、`CString` オブジェクトをパラメーターと戻り値の両方として使用しています。  
  
 [!code-cpp[NVC_ATLMFC_Utilities#197](../atl-mfc-shared/codesnippet/CPP/cstring-argument-passing_1.cpp)]  
  
 [!code-cpp[NVC_ATLMFC_Utilities#198](../atl-mfc-shared/codesnippet/CPP/cstring-argument-passing_2.cpp)]  
  
## 参照  
 [文字列](../atl-mfc-shared/strings-atl-mfc.md)