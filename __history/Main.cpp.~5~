#include <vcl.h>
#pragma hdrstop

#include "Main.h"
#include "uGlobalDefsBase.h"
//---------------------------------------------------------------------------
#pragma package(smart_init)
#pragma resource "*.dfm"
TMainForm *MainForm;
/*
FloatToStrF(this->pRecordBaseItem->fKvFlow, ffFixed, 8, 2);
FormatFloat("0.0", dPodwojnaPrecyzja);
try
{
}
catch(const Exception& e)
{
	MessageBox(NULL, e.Message.c_str(), TEXT("Błąd aplikacji"), MB_OK | MB_ICONERROR | MB_TASKMODAL);
}
*/
/*
	#if defined(_DEBUGINFO_)
		GsDebugClass::WriteDebug(Format("PathData: %s", ARRAYOFCONST((PathData))));
	#endif
	#if defined(_DEBUGINFO_)
		GsDebugClass::WriteDebug("");
	#endif
*/
//StringCchCopyA(STRSAFE_LPSTR pszDest, size_t SizeDest, STRSAFE_LPCSTR pszSrc)

//---------------------------------------------------------------------------
__fastcall TMainForm::TMainForm(TComponent* Owner)
	: TForm(Owner)
/**
	OPIS METOD(FUNKCJI): Główny kontruktor
	OPIS ARGUMENTÓW:
	OPIS ZMIENNYCH:
	OPIS WYNIKU METODY(FUNKCJI):
*/
{
  #if defined(_DEBUGINFO_)
		GsDebugClass::InitDebug();
	#endif
	//---
	Application->OnException = this->_AppException; //Ustawienie obsługi błędów dla całej aplikacji
  #if defined(_DEBUGINFO_)
		GsDebugClass::WriteDebug(Format("Global_cstrWorkDir: \"%s\"", ARRAYOFCONST((Global_cstrWorkDir))));
	#endif
}
//---------------------------------------------------------------------------
__fastcall TMainForm::~TMainForm()
/**
	OPIS METOD(FUNKCJI): Główny destruktor
	OPIS ARGUMENTÓW:
	OPIS ZMIENNYCH:
	OPIS WYNIKU METODY(FUNKCJI):
*/
{
  #if defined(_DEBUGINFO_) //Konsola debuggera
		MessageBox(NULL, TEXT("Wstrzymanie zamykania aplikacji, w celu przeglądu komunikatów konsoli!"), TEXT("Informacje aplikacji"), MB_OK | MB_ICONINFORMATION | MB_TASKMODAL);
		GsDebugClass::CloseDebug();
	#endif
}
//---------------------------------------------------------------------------
void __fastcall TMainForm::_AppException(TObject *Sender, Exception *pException)
/**
	OPIS METOD(FUNKCJI): Główny kontruktor
	OPIS ARGUMENTÓW:
	OPIS ZMIENNYCH:
	OPIS WYNIKU METODY(FUNKCJI):
*/
{
  Application->ShowException(pException);
	this->OnCloseQuery = nullptr;
	this->Close();
	//Application->Terminate(); //Zamknięcie aplikacji
}
//---------------------------------------------------------------------------
