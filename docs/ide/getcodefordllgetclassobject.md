---
title: "GetCodeForDllGetClassObject | Microsoft Docs"
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
  - "GetCodeForDllGetClassObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetCodeForDllGetClassObject メソッド"
ms.assetid: 67b61b3b-9784-494f-ba01-17bffa9941ff
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# GetCodeForDllGetClassObject
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

DLL のクラス オブジェクトのコードを取得します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      function GetCodeForDllGetClassObject(   
   nLineStart,   
   nLineEnd    
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `nLineStart`  
 関数の先頭の 0 から始まる行番号。  
  
 `nLineEnd`  
 関数の末尾の 0 から始まる行番号。  
  
## <a name="return-value"></a>戻り値  
 クラスのオブジェクトを取得するためのコードを含む文字列。  
  
## <a name="remarks"></a>コメント  
 クラスのオブジェクトのコードを取得するには、このメンバー関数を呼び出します。 この関数を呼び出すと、指定した配列の要素を連結して 1 つの文字列が作成されます。  
  
 次の表は、クラス オブジェクトのコードを取得するためのコードを示しています。  
  
|行番号|コード|  
|-----------------|----------|  
|0|AFX_MANAGE_STATE(AfxGetStaticModuleState()) です。|  
|1|場合 (S_OK _AtlModule.GetClassObject (rclsid、riid、ppv) = =)|  
|2|\treturn S_OK です。|  
|3|AfxDllGetClassObject (rclsid、riid、ppv) を返す|  
  
 返される行の各 `GetCodeForDllGetClassObject` 先頭のタブを追加 (`\t`) および末尾"CR LF"(キャリッジ リターン - ライン フィード) 文字のペア (`\r\n`)。  
  
## <a name="example"></a>例  
  
```  
// Get the lines numbered 1 and 2 above  
GetCodeForDllGetClassObject(1, 2)  
  
// returns the following string  
// "\tif (S_OK == _AtlModule.GetClassObject(rclsid, riid, ppv))\r\n\t\treturn S_OK;\r\n"  
  
```  
  
## <a name="see-also"></a>関連項目  
 [共通の JScript 関数による C++ ウィザードのカスタマイズ](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [C++ ウィザードの JScript 関数](../ide/jscript-functions-for-cpp-wizards.md)   
 [カスタム ウィザードの作成](../ide/creating-a-custom-wizard.md)   
 [ウィザードのデザイン](../ide/designing-a-wizard.md)