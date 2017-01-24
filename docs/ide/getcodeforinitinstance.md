---
title: "GetCodeForInitInstance | Microsoft Docs"
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
  - "GetCodeForInitInstance"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetCodeForInitInstance メソッド"
ms.assetid: cfa4cb9f-d1cc-4be6-8db9-c253655b57e4
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# GetCodeForInitInstance
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[InitInstance](../Topic/CWinApp::InitInstance.md) に対して指定されたコードを取得します。  
  
## 構文  
  
```  
  
      function GetCodeForInitInstance(   
   nLineStart,   
   nLineEnd    
);  
```  
  
#### パラメーター  
 `nLineStart`  
 関数の先頭を示す 0 から始まる行番号。  
  
 `nLineEnd`  
 関数の末尾を示す 0 から始まる行番号。  
  
## 戻り値  
 ウィザード インスタンスを初期化するためのコードを含む文字列を返します。  
  
## 解説  
 このメンバー関数を呼び出して、ウィザード インスタンスを初期化するために適切なコードを取得します。  行番号は次のとおりです。  
  
|行番号|InitInstance コード|  
|---------|----------------------|  
|0|`CWinApp::InitInstance();`|  
|1|`return TRUE;`|  
|2|`AfxOleInit();`|  
|3|`// Parse command line for standard shell commands, DDE, file open`|  
|4|`CCommandLineInfo cmdInfo;`|  
|5|`ParseCommandLine(cmdInfo);`|  
|6|`// App was launched with /Embedding or /Automation switch.`|  
|7|`// Run app as automation server.`|  
|8|`if (cmdInfo.m_bRunEmbedded &#124;&#124; cmdInfo.m_bRunAutomated)`|  
|9|`{`|  
|10|`\t// Register class factories via CoRegisterClassObject().`|  
|11|`\tif (FAILED(_AtlModule.RegisterClassObjects(CLSCTX_LOCAL_SERVER, REGCLS_MULTIPLEUSE)))`|  
|12|`\t\treturn FALSE;`|  
|13|`\t// Don't show the main window`|  
|14|`\treturn TRUE;`|  
|15|`}`|  
|16|`// App was launched with /Unregserver or /Unregister switch.`|  
|17|`if (cmdInfo.m_nShellCommand == CCommandLineInfo::AppUnregister)`|  
|18|`{`|  
|19|`\t_AtlModule.UpdateRegistryAppId(FALSE);`|  
|20|`\t_AtlModule.UnregisterServer(TRUE);`|  
|21|`\treturn FALSE;`|  
|22|`}`|  
|23|`// App was launched with /Register or /Regserver switch.`|  
|24|`if (cmdInfo.m_nShellCommand == CCommandLineInfo::AppRegister)`|  
|25|`{`|  
|26|`\t_AtlModule.UpdateRegistryAppId(TRUE);`|  
|27|`\t_AtlModule.RegisterServer(TRUE);`|  
|28|`\treturn FALSE;`|  
|29|`}`|  
  
 返される各行には、`GetCodeForInitInstance` によって、先頭にタブ \(`\t`\)、末尾に "CR\-LF" \(復帰と改行\) 文字のペア \(`\r\n`\) が付け加えられます。  
  
## 使用例  
  
```  
// Get the lines numbered 0 through 2 above  
GetCodeForInitInstance(0, 2)  
  
// returns the following string  
// "\tCWinApp::InitInstance();\r\n\treturn TRUE;\r\n\tAfxOleInit();\r\n"  
  
```  
  
## 参照  
 [共通の JScript 関数による C\+\+ ウィザードのカスタマイズ](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [C\+\+ ウィザードの JScript 関数](../ide/jscript-functions-for-cpp-wizards.md)   
 [カスタム ウィザードの作成](../ide/creating-a-custom-wizard.md)   
 [ウィザードのデザイン](../ide/designing-a-wizard.md)   
 [GetCodeForExitInstance](../Topic/GetCodeForExitInstance.md)