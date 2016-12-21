---
title: "CComBSTR クラス | Microsoft Docs"
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
  - "ATL::CComBSTR"
  - "CComBSTR"
  - "ATL.CComBSTR"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BSTRs, ラッパー"
  - "CComBSTR"
  - "CComBSTR クラス"
ms.assetid: 8fea1879-a05e-47a5-a803-8dec60eaa534
caps.latest.revision: 21
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CComBSTR クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスは、`BSTR` のラッパー クラスです。  
  
## 構文  
  
```  
  
class CComBSTR  
  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CComBSTR::CComBSTR](../Topic/CComBSTR::CComBSTR.md)|コンストラクターです。|  
|[CComBSTR::~CComBSTR](../Topic/CComBSTR::~CComBSTR.md)|デストラクターです。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CComBSTR::Append](../Topic/CComBSTR::Append.md)|`m_str`に文字列を追加します。|  
|[CComBSTR::AppendBSTR](../Topic/CComBSTR::AppendBSTR.md)|`m_str`に `BSTR` を追加します。|  
|[CComBSTR::AppendBytes](../Topic/CComBSTR::AppendBytes.md)|`m_str`に指定したバイト数を追加します。|  
|[CComBSTR::ArrayToBSTR](../Topic/CComBSTR::ArrayToBSTR.md)|セーフ配列の各要素の最初の文字から `BSTR` を作成し、`CComBSTR` のオブジェクトにアタッチします。|  
|[CComBSTR::AssignBSTR](../Topic/CComBSTR::AssignBSTR.md)|`m_str`に `BSTR` を割り当てます。|  
|[CComBSTR::Attach](../Topic/CComBSTR::Attach.md)|`CComBSTR` のオブジェクトに `BSTR` をアタッチします。|  
|[CComBSTR::BSTRToArray](../Topic/CComBSTR::BSTRToArray.md)|0 から始まる 1 次元のセーフ配列を作成します。この配列の各要素は `CComBSTR` オブジェクトから取得した文字です。|  
|[CComBSTR::ByteLength](../Topic/CComBSTR::ByteLength.md)|バイト `m_str` の長さを返します。|  
|[CComBSTR::Copy](../Topic/CComBSTR::Copy.md)|`m_str`のコピーを返します。|  
|[CComBSTR::CopyTo](../Topic/CComBSTR::CopyTo.md)|**\[out\]** のパラメーターで `m_str` のコピーを返します|  
|[CComBSTR::Detach](../Topic/CComBSTR::Detach.md)|`CComBSTR` のオブジェクトからデタッチ `m_str`。|  
|[CComBSTR::Empty](../Topic/CComBSTR::Empty.md)|`m_str`を解放します。|  
|[CComBSTR::Length](../Topic/CComBSTR::Length.md)|`m_str`の長さを返します。|  
|[CComBSTR::LoadString](../Topic/CComBSTR::LoadString.md)|文字列リソースを読み込みます。|  
|[CComBSTR::ReadFromStream](../Topic/CComBSTR::ReadFromStream.md)|ストリームからの `BSTR` のオブジェクトを読み込みます。|  
|[CComBSTR::ToLower](../Topic/CComBSTR::ToLower.md)|文字列を小文字に変換します。|  
|[CComBSTR::ToUpper](../Topic/CComBSTR::ToUpper.md)|文字列を大文字に変換します。|  
|[CComBSTR::WriteToStream](../Topic/CComBSTR::WriteToStream.md)|ストリームに `m_str` を保存します。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[CComBSTR::operator BSTR](../Topic/CComBSTR::operator%20BSTR.md)|`CComBSTR` オブジェクトを `BSTR` にキャストします。|  
|[CComBSTR::operator \!](../Topic/CComBSTR::operator%20!.md)|`m_str`が `NULL`かどうかを `true` か `false`、によって。|  
|[CComBSTR::operator \!\=](../Topic/CComBSTR::operator%20!=.md)|`CComBSTR` と文字列を比較します。|  
|[CComBSTR::operator &](../Topic/CComBSTR::operator%20&.md)|`m_str`のアドレスを返します。|  
|[CComBSTR::operator \+\=](../Topic/CComBSTR::operator%20+=.md)|オブジェクトに `CComBSTR` を追加します。|  
|[CComBSTR::operator \<](../Topic/CComBSTR::operator%20%3C.md)|`CComBSTR` と文字列を比較します。|  
|[CComBSTR::operator \=](../Topic/CComBSTR::operator%20=.md)|`m_str`に値を割り当てます。|  
|[CComBSTR::operator \=\=](../Topic/CComBSTR::operator%20==.md)|`CComBSTR` と文字列を比較します。|  
|[CComBSTR::operator \>](../Topic/CComBSTR::operator%20%3E.md)|`CComBSTR` と文字列を比較します。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CComBSTR::m\_str](../Topic/CComBSTR::m_str.md)|`CComBSTR` オブジェクトに関連付けられた `BSTR` を保持します。|  
  
## 解説  
 `CComBSTR` のクラスは、`BSTR`のラッパーですが、長さ前に付いた文字列の。  長さは、文字列のデータを指定するメモリ位置の整数として格納されます。  
  
 [BSTR](http://msdn.microsoft.com/ja-jp/1b2d7d2c-47af-4389-a6b6-b01b7e915228) は最後の文字がカウントが設定された、文字列内に埋め込まれた null 文字が含まれている場合がないと null で終わります。  The string 長さは、文字数最初の null 文字ではなくによって決まります。  
  
> [!NOTE]
>  `CComBSTR` のクラスは、引数としてその一部のメンバー \(コンストラクター、代入演算子、比較演算子\) を受け取ります ANSI 形式または Unicode 文字列を提供します。  これらの関数の ANSI バージョンは、一時的な Unicode 文字列が頻繁に内部的に作成されるため Unicode 対応するよりも効率です。  効率のは、Unicode バージョンを使用します。  
  
> [!NOTE]
>  Visual Studio .NET で、アップグレードされた検索動作のために以前のリリースでコンパイルしない `bstr = L"String2" + bstr;`のようなコードが実行される `bstr = CStringW(L"String2") + bstr`として代わりに実装する必要があります。  
  
 確認の一覧については `CComBSTR`を使用する場合は、[CComBSTR のプログラミング](../../atl/programming-with-ccombstr-atl.md)を参照してください。  
  
## 必要条件  
 atlbase.h**Header:**  
  
## 参照  
 [クラスの概要](../../atl/atl-class-overview.md)   
 [ATL と MFC の文字列変換マクロ](../Topic/ATL%20and%20MFC%20String%20Conversion%20Macros.md)