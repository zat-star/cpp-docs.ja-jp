---
title: "文字列変換マクロ |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
ms.assetid: 2ff7c0b6-2bde-45fe-897f-6128e18e0c27
caps.latest.revision: 16
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
ms.sourcegitcommit: bb94e24657d16b2a3eda3a770c2b6ae734c6006f
ms.openlocfilehash: e322c3af297c288ec6c9ccdb1c04e58d0a5759ff
ms.lasthandoff: 04/12/2017

---
# <a name="string-conversion-macros"></a>文字列変換マクロ
これらのマクロは、文字列の変換機能を提供します。  
  
 
##  <a name="atl_and_mfc_string_conversion_macros"></a>ATL と MFC 文字列変換マクロ  
 ここで説明する文字列変換マクロは、ATL と MFC の両方に対して有効です。 MFC 文字列変換の詳細については、次を参照してください。 [TN059: を使用して MFC の Mbcs/unicode 変換マクロ](../../mfc/tn059-using-mfc-mbcs-unicode-conversion-macros.md)と[MFC マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)です。  
  
##  <a name="devmode_and_textmetric_string_conversion_macros"></a>DEVMODE と受け取る文字列変換マクロ  
 これらのマクロのコピーを作成する、 [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565)または[受け取る](http://msdn.microsoft.com/library/windows/desktop/dd145132)構造体し、新しい構造内の文字列を新しい文字列型に変換します。 マクロは、新しい構造のスタックにメモリを割り当て、新しい構造体へのポインターを返します。  
  
```
MACRONAME( address_of_structure )
```  
  
### <a name="remarks"></a>コメント  
 例:  
  
 [!code-cpp[NVC_ATL_Utilities # 128](../../atl/codesnippet/cpp/string-conversion-macros_1.cpp)]  
  
 および  
  
 [!code-cpp[NVC_ATL_Utilities # 129](../../atl/codesnippet/cpp/string-conversion-macros_2.cpp)]  
  
 マクロ名、ソース構造に文字列型は左側の (たとえば、 **A**) し、右側の送信先構造での文字列型は、(たとえば、 **W**)。 **A** stands for **LPSTR**, **OLE** stands for `LPOLESTR`, **T** stands for `LPTSTR`, and **W** stands for `LPWSTR`.  
  
 したがって、`DEVMODEA2W`のコピー、`DEVMODE`構造体**LPSTR**に文字列を`DEVMODE`構造体`LPWSTR`文字列、`TEXTMETRICOLE2T`のコピー、`TEXTMETRIC`構造体`LPOLESTR`に文字列を`TEXTMETRIC`構造体`LPTSTR`文字列、およびなどです。  
  
 2 つの文字列に変換された、`DEVMODE`構造体は、デバイス名 ( **dmDeviceName**) と形式名 ( **dmFormName**)。 `DEVMODE`文字列変換マクロも構造体のサイズを更新 ( **dmSize**)。  
  
 4 つの文字列に変換された、`TEXTMETRIC`構造体は、最初の文字 ( **tmFirstChar**)、最後の文字 ( **tmLastChar**)、既定の文字 ( **tmDefaultChar**)、および改行文字 ( **tmBreakChar**)。  
  
 動作、`DEVMODE`と`TEXTMETRIC`文字列変換マクロは、存在する場合、有効なコンパイラ ディレクティブとは異なります。 します。 ソースの型とターゲットの型が同じである場合、変換は実行されません。 コンパイラ ディレクティブ**T**と**OLE**次のようにします。  
  
|有効なコンパイラ ディレクティブ|T の変更後|OLE の変更後|  
|----------------------------------|---------------|-----------------|  
|none|**A**|**W**|  
|**_UNICODE**|**W**|**W**|  
|**OLE2ANSI**|**A**|**A**|  
|**_UNICODE**と**は、OLE2ANSI**|**W**|**A**|  
  
 次の表、`DEVMODE`と`TEXTMETRIC`文字列変換マクロです。  
  
|||  
|-|-|  
|`DEVMODEA2W`|`TEXTMETRICA2W`|  
|`DEVMODEOLE2T`|`TEXTMETRICOLE2T`|  
|`DEVMODET2OLE`|`TEXTMETRICT2OLE`|  
|`DEVMODEW2A`|`TEXTMETRICW2A`|  
  
## <a name="see-also"></a>関連項目  
 [マクロ](../../atl/reference/atl-macros.md)


