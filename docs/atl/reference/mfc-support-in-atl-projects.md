---
title: "ATL プロジェクトでの MFC のサポート | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "vc.atl.addmfc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL プロジェクト, MFC サポート"
ms.assetid: f90b4276-cb98-4c11-902c-9ebcfe6f954b
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# ATL プロジェクトでの MFC のサポート
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ATL プロジェクト ウィザードで \[サポート\] を選択すると、プロジェクトはアプリケーションを MFC アプリケーション オブジェクト \(クラス\) として宣言します。  プロジェクトは MFC ライブラリを初期化し、[CWinApp](../../mfc/reference/cwinapp-class.md) の派生クラス \(*ProjName* クラス\) をインスタンス化します。  
  
 このオプションは、属性なしの ATL DLL プロジェクトだけで使用できます。  
  
```  
class CProjNameApp : public CWinApp  
{  
public:  
  
// Overrides  
   virtual BOOL InitInstance();  
   virtual int ExitInstance();  
   DECLARE_MESSAGE_MAP()  
};  
  
BEGIN_MESSAGE_MAP(CProjNameApp, CWinApp)  
END_MESSAGE_MAP()  
  
CProjNameApp theApp;  
  
BOOL CProjNameApp::InitInstance()  
{  
   return CWinApp::InitInstance();  
}  
  
int CProjNameApp::ExitInstance()  
{  
   return CWinApp::ExitInstance();  
}  
```  
  
 クラス ビューで、アプリケーション オブジェクト クラス、およびその `InitInstance` 関数と `ExitInstance` 関数を表示できます。  
  
## 参照  
 [クラスの追加](../Topic/Adding%20a%20Class%20\(Visual%20C++\).md)   
 [ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)   
 [ATL プロジェクトの既定の構成](../../atl/reference/default-atl-project-configurations.md)