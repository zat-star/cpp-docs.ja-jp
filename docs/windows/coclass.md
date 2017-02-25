---
title: "coclass | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.coclass"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "coclass attribute"
ms.assetid: 42da6a10-3af9-4b43-9a1d-689d00b61eb3
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# coclass
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

COM インターフェイスを実装する COM オブジェクトを作成します。  
  
## 構文  
  
```  
  
[coclass]  
  
```  
  
## 解説  
 **コクラス**  C\+\+ 属性は生成された .idl ファイルはコクラスの構造を配置します。  
  
 コクラスを定義する場合は[uuid](../windows/uuid-cpp-attributes.md)[バージョン](../windows/version-cpp.md)[スレッド](../windows/threading-cpp.md)[vi\_progid](../windows/vi-progid.md) と [ProgID](../Topic/progid.md) の属性を指定できます。  これらのどちらでも指定しない場合が生成されます。  
  
 2 個のヘッダー ファイルにが含まれている場合  **コクラス**  のクラスはGUID を属性付き ATL オブジェクトと属性を指定しない場合コンパイラはこれらのクラスに同じ GUID を使用してMIDL のエラーが発生します。  したがって  **コクラス**  を使用すると`uuid` の属性を使用します。  
  
 **ATL プロジェクト**  
  
 この属性はATL プロジェクトのクラスまたは構造体の定義の前にある場合は:  
  
-   コードまたはデータがオブジェクトの自動登録をサポートするために挿入します。  
  
-   コードまたはデータがオブジェクトの COM クラス ファクトリをサポートするために挿入します。  
  
-   コードまたはデータが **IUnknown** を実行しオブジェクトの COM オブジェクトの作成を行うに挿入します。  
  
 具体的には次の基本クラスはターゲット オブジェクトに追加されます :  
  
-   [CComCoClass のクラス](../Topic/CComCoClass%20Class.md) はオブジェクトの既定のクラス ファクトリと集約モデルを提供します。  
  
-   [CComObjectRootEx のクラス](../atl/reference/ccomobjectrootex-class.md) に [スレッド](../windows/threading-cpp.md) の属性で指定されたスレッド処理モデルのクラスに基づくテンプレートがあります。   **スレッド**  の属性を指定しない場合既定のアパートメント スレッド モデルはです。  
  
-   [IProvideClassInfo2Impl](../atl/reference/iprovideclassinfo2impl-class.md) は [作成](../windows/noncreatable.md) の属性がターゲット オブジェクトに対して指定する追加されます。  
  
 最後に埋め込み IDL を使用して定義されていないデュアル インターフェイスが [IDispatchImpl](../atl/reference/idispatchimpl-class.md) の対応するクラスに置き換えられます。  デュアル インターフェイスに埋め込み IDL で定義されている場合基本クラスのリストに特定のインターフェイスは変更されません。  
  
 **コクラス**  の属性は次の関数を `CComCoClass`基本クラスの静的メソッドとして挿入されたコードまたは `GetObjectCLSID` で使用できるようにするには :  
  
-   `UpdateRegistry` は前のクラス ファクトリを登録します。  
  
-   または `GetObjectCLSID` の登録に関連する対象のクラスの CLSID を取得するために使用できます。  
  
-   **GetObjectFriendlyName** の既定ではは 「形式 \<target *クラス name\>*`Object` 」の文字列。  この関数が既に存在する場合は追加されません。  自動的に生成する場合よりわかりやすい名前を返すため対象クラスにはこの関数を追加します。  
  
-   **GetProgID** は登録に関連する [ProgID](../Topic/progid.md) の属性で指定された文字列を返します。  
  
-   **GetVersionIndependentProgID** に **GetProgID** と同じ機能を持ちますが[vi\_progid](../windows/vi-progid.md) で指定された文字列を返します。  
  
 COM マップに関連するターゲット クラスに次の変更が行われます。:  
  
-   COM マップ先はクラスがから派生する [COM インターフェイスのエントリ ポイント](../mfc/com-interface-entry-points.md) で指定されているすべてのエントリは[集約](../windows/aggregates.md) の属性で必要な属性と属性はすべてのインターフェイスのエントリが追加されます。  
  
-   [OBJECT\_ENTRY\_AUTO](../Topic/OBJECT_ENTRY_AUTO.md) マクロは COM マップに挿入されます。  このマクロは機能の点で [OBJECT\_ENTRY](http://msdn.microsoft.com/ja-jp/abd10ee2-54f0-4f94-9ec2-ddf8f4c8c8cd) に似ていますが対象のクラスの COM マップの一部である必要はありません。  
  
 クラスの .idl ファイル内に生成されるクラスとコクラスの名前と同じ名前になります。  たとえばMIDL で生成されるヘッダー ファイルを使用してクライアントのコクラス CMyClass のクラス ID にアクセスするには次の例を使用 CLSID\_CMyClass 参照します。  
  
## 使用例  
 次のコードは  **コクラス**  属性の使用方法を示します :  
  
```  
// cpp_attr_ref_coclass1.cpp  
// compile with: /LD  
#include "unknwn.h"  
[module(name="MyLib")];  
  
[ object, uuid("00000000-0000-0000-0000-000000000001") ]  
__interface I {  
   HRESULT func();  
};  
  
[coclass, progid("MyCoClass.coclass.1"), vi_progid("MyCoClass.coclass"),   
appobject, uuid("9E66A294-4365-11D2-A997-00C04FA37DDB")]  
class CMyClass : public I {};  
```  
  
 次の例では  **コクラス**  の属性によって挿入されたコードに表示される関数の既定の実装をオーバーライドする方法を説明します。  挿入されたコードの表示の詳細については [\/Fx](../build/reference/fx-merge-injected-code.md) を参照してください。  このクラスで使用するインターフェイス挿入されるコードでの基本クラスが表示されます。    クラスが挿入されたコードが既定で含まれておりコクラスのベースとして明示的にそのクラスを指定する場合はさらに属性プロバイダーはコード内の指定した形式を使用します。  
  
```  
// cpp_attr_ref_coclass2.cpp  
// compile with: /LD  
#include <atlbase.h>  
#include <atlcom.h>  
#include <atlwin.h>  
#include <atltypes.h>  
#include <atlctl.h>  
#include <atlhost.h>  
#include <atlplus.h>  
  
[module(name="MyLib")];  
  
[object, uuid("00000000-0000-0000-0000-000000000000")]  
__interface bb {};  
  
[coclass, uuid("00000000-0000-0000-0000-000000000001")]  
class CMyClass : public bb {  
public:  
   // by adding the definition of UpdateRegistry to your code,   
   // the function will not be included in the injected code  
   static HRESULT WINAPI UpdateRegistry(BOOL bRegister) {  
      // you can add to the default implementation  
      CRegistryVirtualMachine rvm;  
      HRESULT hr;  
      if (FAILED(hr = rvm.AddStandardReplacements()))  
         return hr;  
      rvm.AddReplacement(_T("FriendlyName"), GetObjectFriendlyName());  
      return rvm.VMUpdateRegistry(GetOpCodes(), GetOpcodeStringVals(),  
         GetOpcodeDWORDVals(), GetOpcodeBinaryVals(), bRegister);  
   }  
};  
```  
  
## 必要条件  
  
### 属性コンテキスト  
  
|||  
|-|-|  
|**対象**|**クラス**  `struct`|  
|**複数回の適用**|Ｘ|  
|**必要な属性**|なし|  
|**無効な属性**|なし|  
  
 属性コンテキストの詳細については、「[属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## 参照  
 [IDL Attributes](../windows/idl-attributes.md)   
 [COM Attributes](../Topic/COM%20Attributes.md)   
 [Class Attributes](../windows/class-attributes.md)   
 [Typedef, Enum, Union, and Struct Attributes](../windows/typedef-enum-union-and-struct-attributes.md)   
 [appobject](../Topic/appobject.md)