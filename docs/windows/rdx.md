---
title: "rdx |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- vc-attr.rdx
dev_langs:
- C++
helpviewer_keywords:
- rdx attribute
ms.assetid: ff8e4312-c1ad-4934-bdaa-86f54409651e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d656af60ec14309227fc73d81bd0f14638637d48
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="rdx"></a>rdx
レジストリ キーを作成するか、既存のレジストリ キーを変更します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      [ rdx(   
   key,   
   valuename=NULL,   
   regtype   
) ]  
```  
  
#### <a name="parameters"></a>パラメーター  
 `key`  
 作成または開くのためのキーの名前です。  
  
 `valuename`(省略可能)  
 設定する値 フィールドを指定します。 キーにもこの名前の値フィールドが既に存在しない場合が追加されます。  
  
 *regtype*  
 追加されるレジストリ キーの型。 次のいずれかになります:**テキスト**、 **dword**、**バイナリ**、または`CString`です。  
  
## <a name="remarks"></a>コメント  
 **Rdx** C++ 属性を作成または COM コンポーネントの既存のレジストリ キーを変更します。 属性は、対象のメンバーを実装するオブジェクトを BEGIN_RDX_MAP マクロを追加します。 `RegistryDataExchange`、レジストリ データ メンバーの間でデータを転送する BEGIN_RDX_MAP マクロの結果として挿入された関数を使用できます  
  
 この属性を組み合わせて使用することができます、[コクラス](../windows/coclass.md)、 [progid](../windows/progid.md)、または[vi_progid](../windows/vi-progid.md)属性または次のいずれかのことを意味するその他の属性です。  
  
## <a name="requirements"></a>必要条件  
  
### <a name="attribute-context"></a>属性コンテキスト  
  
|||  
|-|-|  
|**対象**|**クラス**または`struct`メンバー|  
|**反復可能**|×|  
|**必要な属性**|なし|  
|**無効な属性**|なし|  
  
 属性コンテキストの詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## <a name="example"></a>例  
 次のコードでは、CMyClass COM コンポーネントを記述するシステムに MyValue をというレジストリ キーを追加します。  
  
```  
// cpp_attr_ref_rdx.cpp  
// compile with: /LD /link /OPT:NOREF  
#define _ATL_ATTRIBUTES  
#include "atlbase.h"  
  
[module (name="MyLib")];  
  
class CMyClass {  
public:  
   CMyClass() {  
      strcpy_s(m_sz, "SomeValue");  
   }  
  
   [ rdx(key = "HKCR\\MyApp.MyApp.1", valuename = "MyValue", regtype = "text")]   
   char m_sz[256];  
};  
```  
  
## <a name="see-also"></a>参照  
 [COM 属性](../windows/com-attributes.md)   
 [registration_script](../windows/registration-script.md)   
