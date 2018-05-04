---
title: MFC ActiveX コントロール ウィザード、アプリケーションの設定 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vc.appwiz.mfc.ctl.appset
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX Control Wizard, application settings
ms.assetid: 48475194-cc63-467f-8499-f142269a4c1c
caps.latest.revision: 12
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4b63507ba50f5f9d7dfb0fe5487e2758ced02cdd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="application-settings-mfc-activex-control-wizard"></a>[アプリケーションの設定] \(MFC ActiveX コントロール ウィザード)
MFC ActiveX コントロール ウィザードのこのページを使用して、基本的な機能を設計して新しい MFC ActiveX プロジェクトに追加します。 これらの設定は、アプリケーション自体に適用され、コントロールの特定の機能や要素には適用されません。  
  
 **ランタイム ライセンス**  
 コントロールと共に配布するユーザー ライセンス ファイルを生成する場合はこのオプションを選択します。 ライセンスは、テキスト ファイル *projname*.lic です。 このファイルは、デザイン時環境でコントロールのインスタンスを作成できるように、コントロールの DLL と同じディレクトリに配置する必要があります。 通常、コントロールと共にこのファイルを配布しますが、お客様は配布しません。  
  
 **ヘルプ ファイルを生成します。**  
 スタブのヘルプ ファイルを生成し、コントロールのヘルプを含むプロジェクトを構成するには、このオプションを選択します。 このオプションを指定せずに作成された既定のプロジェクトは、 **情報** ボックスのみを生成します。このボックスは、ユーザーがコントロールを右クリックした時、F1 キーを使用した時、またはコントロールのコンテナーの **ヘルプ** をクリックした時に表示されます。  
  
> [!NOTE]
>  ヘルプを表示する方法は、コントロールがコンテナーとやり取りする方法によって異なります。 ヘルプをコンテナーに含めるには、適切にヘルプを表示するようコントロールとコンテナー間のメッセージを処理する必要があります。  
  
 ウィザードを使用してヘルプ ファイルを生成する場合、プロジェクトに次を含めます。  
  
-   .vcxproj ファイルには、プロジェクトがビルドされたときにヘルプ ファイルをビルドして構成するためのコードが含まれています。  
  
-   ファイル*projnamePropPage*.cpp ファイルが含まれています、 [SetHelpInfo](../../mfc/reference/colepropertypage-class.md#sethelpinfo)コンス トラクターで機能します。  
  
-   ファイルの projname.hpj は、ActiveX コントロールのヘルプ ファイルを作成するためにヘルプ コンパイラで使用されるヘルプ プロジェクト ファイルです。 .hpj ファイルは、ヘルプ ファイルのビルド方法と、ヘルプ ファイルに含まれる追加のファイル (ビットマップなど) のパスに関する情報を含むテキスト ファイルです。  
  
-   プロジェクトには、プロジェクトのヘルプのビットマップ ファイルおよびヘルプ トピック ファイルを格納する HLP ディレクトリが含まれています (*projname*.rtf)。 このヘルプ トピック ファイルには、多くの ActiveX コントロールでサポートされるプロパティ、イベント、およびメソッドに関する標準的なヘルプ トピックが含まれています。 .rtf ファイルを編集して、特定のヘルプ トピックを追加または削除できます。  
  
## <a name="see-also"></a>参照  
 [MFC ActiveX コントロール ウィザード](../../mfc/reference/mfc-activex-control-wizard.md)   
 [MFC ActiveX コントロール ウィザード、コントロール名](../../mfc/reference/control-names-mfc-activex-control-wizard.md)   
 [[コントロールの設定] (MFC ActiveX コントロール ウィザード)](../../mfc/reference/control-settings-mfc-activex-control-wizard.md)

