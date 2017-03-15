---
title: "wbuffer_convert クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "stdext::cvt::wbuffer_convert"
  - "wbuffer_convert"
  - "stdext.cvt.wbuffer_convert"
  - "cvt.wbuffer_convert"
  - "cvt::wbuffer_convert"
  - "wbuffer/stdext::cvt::wbuffer_convert"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "wbuffer_convert クラス"
ms.assetid: 4a56f9bf-4138-4612-b516-525fea401358
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# wbuffer_convert クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

バイト ストリーム バッファーとの間の要素の転送を制御するストリーム バッファーを説明します。  
  
## 構文  
  
```  
template<class Codecvt,  
    class Elem = wchar_t,  
    class Traits = std::char_traits<Elem>  
>  
    class wbuffer_convert  
        : public std::basic_streambuf<Elem, Traits>  
```  
  
#### パラメーター  
  
|パラメーター|説明|  
|------------|--------|  
|`Codecvt`|変換オブジェクトを表す[ロケール](../standard-library/locale-class.md) ファセット。|  
|`Elem`|ワイド文字要素型。|  
|`Traits`|*Elem* と関連付けられている特徴。|  
  
## 解説  
 このテンプレート クラスは、文字の特徴がクラス `Traits` によって記述される型 `_Elem` の要素の、型 `std::streambuf` のバイト ストリーム バッファーとの間での転送を制御するストリーム バッファーについて説明します。  
  
 `Elem` 値のシーケンスとマルチバイト シーケンスとの間の変換は、クラス `Codecvt<Elem, char, std::mbstate_t>` のオブジェクトによって実行されます。このことは、標準コード変換ファセット `std::codecvt<Elem, char, std::mbstate_t>` の要件を満たしています。  
  
 このテンプレート クラスのオブジェクトは、以下のものを格納します。  
  
-   基になるバイト ストリーム バッファーへのポインター  
  
-   割り当てられた変換オブジェクトへのポインター \([wbuffer\_convert](../standard-library/wbuffer-convert-class.md) オブジェクトが破棄されると解放される\)  
  
-   型 [state\_type](../Topic/wbuffer_convert::state_type.md) の変換状態オブジェクト  
  
### コンストラクター  
  
|||  
|-|-|  
|[wbuffer\_convert](../Topic/wbuffer_convert::wbuffer_convert.md)|`wbuffer_convert` 型のオブジェクトを構築します。|  
  
### Typedefs  
  
|||  
|-|-|  
|[state\_type](../Topic/wbuffer_convert::state_type.md)|変換状態を表す型。|  
  
### メンバー関数  
  
|||  
|-|-|  
|[rdbuf](../Topic/wbuffer_convert::rdbuf.md)|バイト ストリーム バッファーを返します。|  
|[状態](../Topic/wbuffer_convert::state.md)|変換の状態を表すオブジェクトを返します。|  
  
## 必要条件  
 **ヘッダー:** \<locale\>  
  
 **名前空間:** std