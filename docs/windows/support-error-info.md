---
title: "support_error_info |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.support_error_info
dev_langs: C++
helpviewer_keywords: support_error_info attribute
ms.assetid: 20a2b55c-4738-4b35-a71d-e5e9c3a7e3bc
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b8fec0ff1f76485700199847615ac2d8fcf9e5eb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="supporterrorinfo"></a>support_error_info
詳細なエラーを返すためのサポートを実装します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      [ support_error_info(  
   error_interface=uuid  
) ]  
```  
  
#### <a name="parameters"></a>パラメーター  
 **error_interface**  
 **IErrorInfo**を実装するインターフェイスの識別子。  
  
## <a name="remarks"></a>コメント  
 **support_error_info** C++ 属性は、ターゲット オブジェクトで発生した詳細なコンテキスト エラーをクライアントに返すためのサポートを実装します。 オブジェクトがエラーをサポートするには、 **IErrorInfo** インターフェイスのメソッドがオブジェクトによって実装されている必要があります。 詳細については、「 [IDispatch と IErrorInfo のサポート](../atl/supporting-idispatch-and-ierrorinfo.md)」を参照してください。  
  
 この属性により、 [ISupportErrorInfoImpl](../atl/reference/isupporterrorinfoimpl-class.md) クラスが基本クラスとしてターゲット オブジェクトに追加されます。 その結果、 **ISupportErrorInfo** が既定で実装され、これを単一のインターフェイスでオブジェクトのエラーが生成される際に使用できるようになります。  
  
## <a name="example"></a>例  
 次のコードでは、 **ISupportErrorInfo** インターフェイスの既定のサポートが `CMyClass` オブジェクトに追加されます。  
  
```  
// cpp_attr_ref_support_error_info.cpp  
// compile with: /LD  
#define _ATL_ATTRIBUTES  
#include "atlbase.h"  
#include "atlcom.h"  
  
[module (name="mymod")];  
[object, uuid("f0b17d66-dc6e-4662-baaf-76758e09c878")]  
__interface IMyErrors  
{  
};  
  
[ coclass, support_error_info("IMyErrors"),  
  uuid("854dd392-bdc7-4781-8667-8757936f2a4f") ]  
class CMyClass  
{  
};  
```  
  
## <a name="requirements"></a>必要条件  
  
### <a name="attribute-context"></a>属性コンテキスト  
  
|||  
|-|-|  
|**対象**|**クラス**|  
|**反復可能**|[はい]|  
|**必要な属性**|なし|  
|**無効な属性**|なし|  
  
 属性コンテキストの詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## <a name="see-also"></a>参照  
 [COM 属性](../windows/com-attributes.md)   
 [クラス属性](../windows/class-attributes.md)   
