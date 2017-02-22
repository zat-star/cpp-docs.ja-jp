---
title: "wstring_convert クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "cvt.wstring_convert"
  - "wstring_convert"
  - "stdext::cvt::wstring_convert"
  - "cvt::wstring_convert"
  - "wstring/stdext::cvt::wstring_convert"
  - "stdext.cvt.wstring_convert"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "wstring_convert クラス"
ms.assetid: e34f5b65-d572-4bdc-ac69-20778712e376
caps.latest.revision: 25
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 25
---
# wstring_convert クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

テンプレート クラス `wstring_convert` は、ワイド文字列とバイト文字列の間の変換を実行します。  
  
## 構文  
  
```  
template<  
    class Codecvt,  
    class Elem = wchar_t  
>  
class wstring_convert  
```  
  
#### パラメーター  
 Codecvt  
 変換オブジェクトを表す[ロケール](../standard-library/locale-class.md) ファセット。  
  
 Elem  
 ワイド文字要素型。  
  
## 解説  
 このテンプレート クラスは、クラス `std::basic_string<Elem>` のワイド文字列オブジェクトとクラス `std::basic_string<char>` \(`std::string` とも呼ばれます\) のバイト文字列オブジェクトの間の変換を制御するオブジェクトを表します。 このテンプレート クラスは、`wide_string` 型と `byte_string` 型をこれら 2 つの型のシノニムとして定義します。`Elem` 値のシーケンス \(`wide_string` オブジェクトに格納\) とマルチバイト シーケンス \(`byte_string` オブジェクトに格納\) の間の変換は、クラス `Codecvt<Elem, char, std::mbstate_t>` のオブジェクトによって実行されます。このことは、標準コード変換ファセット `std::codecvt<Elem, char, std::mbstate_t>` の要件を満たしています。  
  
 このテンプレート クラスのオブジェクトは、以下のものを格納します。  
  
-   エラーに表示するバイト文字列  
  
-   エラーに表示するワイド文字列  
  
-   割り当てられた変換オブジェクトへのポインター \(wbuffer\_convert オブジェクトが破棄されると解放される\)  
  
-   型 [state\_type](../Topic/wstring_convert::state_type.md) の変換状態オブジェクト  
  
-   変換の数  
  
### コンストラクター  
  
|||  
|-|-|  
|[wstring\_convert](../Topic/wstring_convert::wstring_convert.md)|`wstring_convert` 型のオブジェクトを構築します。|  
  
### Typedefs  
  
|||  
|-|-|  
|[byte\_string](../Topic/wstring_convert::byte_string.md)|バイト文字列を表す型。|  
|[wide\_string](../Topic/wstring_convert::wide_string.md)|ワイド文字列を表す型。|  
|[state\_type](../Topic/wstring_convert::state_type.md)|変換状態を表す型。|  
|[int\_type](../Topic/wstring_convert::int_type.md)|整数を表す型。|  
  
### メンバー関数  
  
|||  
|-|-|  
|[from\_bytes](../Topic/wstring_convert::from_bytes.md)|バイト文字列をワイド文字列に変換します。|  
|[to\_bytes](../Topic/wstring_convert::to_bytes.md)|ワイド文字列をバイト文字列に変換します。|  
|[converted](../Topic/wstring_convert::converted.md)|成功した変換の数を返します。|  
|[状態](../Topic/wstring_convert::state.md)|変換の状態を表すオブジェクトを返します。|  
  
## 必要条件  
 **ヘッダー:** \<locale\>  
  
 **名前空間:** std