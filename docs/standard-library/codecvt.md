---
title: "&lt; codecvt &gt; | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "codecvt"
  - "std::<codecvt>"
  - "std.<codecvt>"
  - "<codecvt>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "codecvt ヘッダー"
ms.assetid: d44ee229-00d5-4761-9b48-0c702122789d
caps.latest.revision: 21
caps.handback.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# &lt; codecvt &gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

テンプレート クラスに基づいてオブジェクトを記述するいくつかのテンプレート クラスを定義して [codecvt](../standard-library/codecvt-class.md)します。 これらのオブジェクトになる [ロケールのファセット](../standard-library/locale-class.md#facet_class) 型の値のシーケンスの間の変換を制御する `Elem` と型の値のシーケンス `char`します。  
  
## <a name="syntax"></a>構文  
  
```  
#include <codecvt>  
  
```  
  
## <a name="remarks"></a>解説  
 このヘッダーで宣言されているロケールのファセットは、いくつかの文字エン コードの間で変換します。 ワイド文字 (固定サイズの整数で、プログラム内で格納されます)。  
  
-   UCS 4 は、プログラム内でエンコードされた Unicode (ISO 10646)  
  
-   UCS 4 は、32 ビット整数値として、プログラム内でエンコードされた Unicode (ISO 10646) です。  
  
-   Ucs-2 は、プログラム内でエンコードされた Unicode です。  
  
-   Ucs-2 とは、16 ビット整数値として、プログラム内でエンコードされた Unicode です。  
  
-   Utf-16 がいずれかとして、プログラム内でエンコードされた Unicode です。  
  
-   Utf-16 とは、1 つまたは 2 つの 16 ビット整数値として、プログラム内でエンコードされた Unicode です。 (これが満たしていないこと、有効なワイド文字のエンコードの標準の C または C++ の標準のすべての要件に注意してください。 しかしこれは広く使用ようです。)  
  
 バイト ストリーム (ファイルに格納されている、バイト シーケンスとして送信またはの配列で、プログラム内に格納された `char`)。  
  
-   Utf-8 でエンコードされた Unicode は、します。  
  
-   Utf-8 が、Unicode のバイト ストリーム内に確定的なバイト順序を持つ 1 つまたは複数の 8 ビット バイトでエンコードされています。  
  
-   UTF 16LE が Unicode エンコーディング  
  
-   UTF 16LE は Unicode エンコードを utf-16 バイト ストリーム内で各 16 ビット整数の最初の下位バイト以下の 2 つの 8 ビット バイトとして表示されます。  
  
-   UTF 16BE が Unicode エンコーディング  
  
-   UTF 16BE は Unicode エンコードを utf-16 バイト ストリーム内で各 16 ビット整数の最初の 2 つの 8 ビット バイトより重要なバイトとして表示されます。  
  
### <a name="enumerations"></a>列挙  
  
|||  
|-|-|  
|[codecvt_mode](../Topic/%3Ccodecvt%3E%20enums.md#codecvt_mode_enumeration)|ロケールのファセットの構成情報を指定します。|  
  
### <a name="classes"></a>クラス  
  
|||  
|-|-|  
|[codecvt_utf8](../Topic/%3Ccodecvt%3E%20functions.md#codecvt_utf8)|ワイド文字の ucs-2 または ucs-4、としてエンコードおよび utf-8 としてエンコードされたバイト ストリーム間で変換されるロケールのファセットを表します。|  
|[codecvt_utf8_utf16](%3Ccodecvt%3E%20functions.md#codecvt_utf8_utf16)|ワイド文字の utf-16 としてエンコードおよび utf-8 としてエンコードされたバイト ストリーム間で変換されるロケールのファセットを表します。|  
|[codecvt_utf16](../Topic/%3Ccodecvt%3E%20functions.md#codecvt_utf16)|ワイド文字の ucs-2 または ucs-4 としてエンコードし、UTF 16LE または UTF 16BE としてエンコードされたバイト ストリーム間で変換されるロケールのファセットを表します。|  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \< codecvt>  
  
 **名前空間:** stdt  
  
## <a name="see-also"></a>参照  
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)




