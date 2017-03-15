---
title: "/INTEGRITYCHECK (シグネチャ確認が必要) | Microsoft Docs"
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
ms.assetid: 9e738825-2c98-40cd-8ad2-5d0d9c14893e
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# /INTEGRITYCHECK (シグネチャ確認が必要)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

読み込み時にバイナリ イメージのデジタル署名を確認する必要があることを指定します。  
  
```  
/INTEGRITYCHECK[:NO]  
```  
  
## 解説  
 既定では、**\/INTEGRITYCHECK** は無効になっています。  
  
 **\/INTEGRITYCHECK** オプションは、Windows でイメージを読み込むために、\(DLL ファイルまたは実行可能ファイルの PE ヘッダーに\) メモリ マネージャーによるデジタル署名のためのフラグを設定します。  このオプションは、特定の Windows 機能によって読み込まれるカーネル モード コードを実装する、32 ビットと 64 ビットの両方の DLL に対して設定する必要があり、Windows Vista、[!INCLUDE[win7](../../build/includes/win7_md.md)]、[!INCLUDE[win8](../../build/includes/win8_md.md)]、[!INCLUDE[winsvr08](../../build/includes/winsvr08_md.md)]、[!INCLUDE[winserver8](../../build/includes/winserver8_md.md)] のすべてのデバイス ドライバーに推奨されます。  Windows Vista 以前の Windows は、このフラグを無視します。  詳細については、「[Forced Integrity Signing of Portable Executable \(PE\) files \(ポータブル実行可能 \(PE\) ファイルの整合性の署名を強制的に実行\)](http://social.technet.microsoft.com/wiki/contents/articles/255.forced-integrity-signing-of-portable-executable-pe-files.aspx)」を参照してください。  
  
### このリンカー オプションを Visual Studio で設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[方法 : プロジェクト プロパティ ページを開く](../../misc/how-to-open-project-property-pages.md)」を参照してください。  
  
2.  **\[構成プロパティ\]** ノードを展開します。  
  
3.  **\[リンカー\]** ノードを展開します。  
  
4.  **\[コマンド ライン\]** プロパティ ページを選択します。  
  
5.  **\[追加オプション\]** に、`/INTEGRITYCHECK` または `/INTEGRITYCHECK:NO` を入力します。  
  
## 参照  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)   
 [Forced Integrity Signing of Portable Executable \(PE\) files \(ポータブル実行可能 \(PE\) ファイルの整合性の署名を強制的に実行\)](http://social.technet.microsoft.com/wiki/contents/articles/255.forced-integrity-signing-of-portable-executable-pe-files.aspx)   
 [カーネル モードのコード署名の手順](http://msdn.microsoft.com/windows/hardware/gg487328.aspx)   
 [Windows 7 と Windows Server 2008 R2 での AppInit DLL](http://msdn.microsoft.com/windows/hardware/gg463040.aspx)