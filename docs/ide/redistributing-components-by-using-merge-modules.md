---
title: "マージ モジュールを使用したコンポーネントの再配布 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "マージ モジュール, 使用"
  - "再頒布 (アプリケーションを), 使用 (マージ モジュールを)"
ms.assetid: 93b84211-bf9b-4a78-9f22-474ac2ef7840
caps.latest.revision: 21
caps.handback.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# マージ モジュールを使用したコンポーネントの再配布
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] には、アプリケーションと共に再頒布することがライセンスされている [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] コンポーネントごとに[マージ モジュール](http://msdn.microsoft.com/library/aa367434)が用意されています。  マージ モジュールが Windows インストーラーのセットアップ ファイルにコンパイルされるときに、特定のプラットフォームのコンピューターへの特定の DLL の配置が有効になります。  セットアップ ファイルでは、そのマージ モジュールがアプリケーションの必須コンポーネントであることを指定します。  [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] をインストールすると、マージ モジュールは \\Program Files\\Common Files\\Merge Modules\\ にインストールされます \(再頒布できるのは非デバッグ バージョンの [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] DLL だけです\)。詳細については、「[Visual C\+\+ ファイルの再配布](../Topic/Redistributing%20Visual%20C++%20Files.md)」を参照してください。このサイトには、再頒布用にライセンスされたマージ モジュールの一覧へのリンクもあります。  
  
 マージ モジュールを使用すると、再頒布可能な [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] DLL を %SYSTEMROOT%\\system32\\ フォルダーにインストールできます \([!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] 自体がこの方法を使用します\)。ただし、このフォルダーへのインストールは、インストールしているユーザーに管理者権限がないと失敗します。  
  
 アプリケーションにサービスを提供する必要がある場合、また、複数のバージョンの DLL に依存している場合は、マージ モジュールを使用することはお勧めしません。  1 つの DLL にさまざまなバージョンの DLL がある場合、その複数バージョンの DLL に対する複数のマージ モジュールを 1 つのインストーラーに含めることはできません。また、マージ モジュールによって、アプリケーションとは別に DLL にサービスを提供することが難しくなります。  代わりに、[!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] 再頒布可能パッケージをインストールすることをお勧めします。  
  
## 参照  
 [Visual C\+\+ ファイルの再配布](../Topic/Redistributing%20Visual%20C++%20Files.md)