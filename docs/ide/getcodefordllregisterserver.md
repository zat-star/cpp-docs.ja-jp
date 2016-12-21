---
title: "GetCodeForDllRegisterServer | Microsoft Docs"
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
  - "GetCodeForDllRegisterServer"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetCodeForDllRegisterServer メソッド"
ms.assetid: 2fe733ad-3f1e-4020-9ce3-68956da7d41d
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# GetCodeForDllRegisterServer
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

サーバーを登録するのに適切なコードを取得します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      function GetCodeForDllRegisterServer(   
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
 サーバーを登録するためのコードを含む文字列  
  
## <a name="remarks"></a>コメント  
 サーバーを登録するための適切なコードを取得するには、このメンバー関数を呼び出します。  
  
|行番号|コード|  
|-----------------|----------|  
|0|AFX_MANAGE_STATE(AfxGetStaticModuleState()) です。|  
|1|_AtlModule.UpdateRegistryAppId(TRUE) です。|  
|2|HRESULT hRes = _AtlModule.RegisterServer(TRUE) です。|  
|3|場合 (hRes! S_OK を =)|  
|4|\treturn hRes です。|  
|5|場合があります。COleObjectFactory::UpdateRegistryAll(TRUE))|  
|6|\treturn ResultFromScode(SELFREG_E_CLASS) です。|  
|7|S_OK を返す|  
  
 各が返される行 `GetCodeForDllRegisterServer` 先頭のタブを追加 (`\t`) および末尾"CR LF"(キャリッジ リターン - ライン フィード) 文字のペア (`\r\n`)。  
  
## <a name="example"></a>例  
  
```  
// Get the lines numbered 2 and 3 above  
GetCodeForDllRegisterServer(2, 3)  
  
// returns the following string  
// "\tHRESULT hRes = _AtlModule.RegisterServer(TRUE);\r\n\tif (hRes != S_OK)\r\n"  
  
```  
  
## <a name="see-also"></a>関連項目  
 [共通の JScript 関数による C++ ウィザードのカスタマイズ](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [C++ ウィザードの JScript 関数](../ide/jscript-functions-for-cpp-wizards.md)   
 [カスタム ウィザードの作成](../ide/creating-a-custom-wizard.md)   
 [ウィザードのデザイン](../ide/designing-a-wizard.md)   
 [GetCodeForDllUnregisterServer](../ide/getcodefordllunregisterserver.md)