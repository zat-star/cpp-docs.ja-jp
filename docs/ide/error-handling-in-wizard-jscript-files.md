---
title: "ウィザードの JScript ファイルでのエラー処理 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "エラー処理, JScript"
  - "JScript, 処理 (エラーを)"
  - "ウィザードの JScript でのエラー処理"
ms.assetid: 6df3ba46-7ab6-484c-ac45-b08f4b6a5900
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# ウィザードの JScript ファイルでのエラー処理
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ウィザードを作成すると、プロジェクトには Default.js ファイルと Common.js ファイルがインクルードされます。  これらのファイルを使用して、プロジェクトをカスタマイズします。  詳細については、「[JScript ファイル](../ide/jscript-file.md)」を参照してください。  
  
 プロジェクトにはエラー処理を組み込む必要があります。  エラー処理を組み込むコードの例を次に示します。  
  
### JScript でエラーを処理するには  
  
1.  ユーザーが \[完了\] をクリックしたときにエラーをキャッチするには、次のコードを使用します。  
  
    ```  
    function OnFinish(selProj, Class)  
    {  
       try  
       {  
          .....  
       }  
       catch(e)  
       {  
          if (e.description.length != 0)  
             SetErrorInfo(e.description, e.number);  
          return e.number  
       }  
    }  
    ```  
  
2.  スクリプトで呼び出された任意のヘルパー スクリプト関数から `e` をスローします。  
  
    ```  
    function ExtenderFromType(strVariableType)  
    {  
       try  
       {  
          ....  
       }  
       catch(e)  
       {  
          throw e;  
       }  
    }  
    ```  
  
3.  **PREPROCESS\_FUNCTION** パラメーターが [.vsz ファイル](../ide/dot-vsz-file-project-control.md)にある場合、ウィザードは [CanAddATLClass](../ide/jscript-functions-for-cpp-wizards.md) を呼び出します。  呼び出しが失敗した場合は、[SetErrorInfo](../ide/seterrorinfo.md) を使用して false を返します。  
  
    ```  
    function CanAddATLClass(oProj, oObject)  
    {  
       try  
       {  
          if (!IsATLProject(oProj))  
          {  
             if (!IsMFCProject(oProj, true))  
             {     
                var L_CanAddATLClass_Text = "ATL classes can only be added  
     to ATL, MFC EXE and MFC regular DLL projects.";  
                wizard.ReportError(L_CanAddATLClass_Text);  
                return false;  
             }  
             else  
             {  
                .....  
                var bRet = AddATLSupportToProject(oProj);  
                .....  
                return bRet;  
             }  
          }  
          return true;  
       }  
       catch(e)  
       {  
          throw e;  
       }  
    }  
    ```  
  
4.  **\[新しいプロジェクト\]** ダイアログ ボックスまたは **\[新しい項目の追加\]** ダイアログ ボックスに戻る必要がある場合は、**VS\_E\_WIZBACKBUTTONPRESS** を返します。  
  
    ```  
    function OnFinish(selProj, Class)  
    {  
       ....  
       if (!CheckAddtoProject(selProj))  
       {  
          return VS_E_WIZARDBACKBUTTONPRESS;  
       }  
    }  
    ```  
  
## 参照  
 [ウィザード用に作成されるファイル](../ide/files-created-for-your-wizard.md)   
 [ウィザードのカスタマイズ](../ide/customizing-your-wizard.md)