// Passport

#include <iostream>
using namespace std;

class Passport {
protected:
	string name;
	string surname;
	string lastname;
	string passport_series;
	string passport_number;
public:
	Passport() {
		name = nullptr;
		surname = nullptr;
		lastname = nullptr;
		passport_number = nullptr;
		passport_series = nullptr;
	}
	Passport(string _name, string _surname, string _lastname, string pas_ser, string pas_num) {
		name = _name;
		surname = _surname;
		lastname = _lastname;
		passport_series = pas_ser;
		passport_number = pas_num;
	}
	void Output() {
		cout << "Name: " << name << endl;
		cout << "Surname: " << surname << endl;
		cout << "Lastname: " << lastname << endl;
		cout << "Passport number: " << passport_number << endl;
		cout << "Passport series: " << passport_series << endl;
	}
};

class ForeignPassport : public Passport {
	string Visas;
	string ForeigPass_number;
public:
	ForeignPassport() {
		Visas = nullptr;
		ForeigPass_number = nullptr;
	}
	ForeignPassport(string _name, string _surname, string _lastname, string pas_ser, string pas_num, string _ForPass_number, string visas)
		: Passport(_name, _surname, _lastname, pas_ser, pas_num)
	{
		Visas = visas;
		ForeigPass_number = _ForPass_number;
	}
	void Output() {
		Passport::Output();
		cout << "Foreing Passport number: " << ForeigPass_number << endl;
		cout << "Visas: " << Visas << endl;
	}
};

int main() {
	ForeignPassport my_passport{ "Alex", "Salnik", "Eduardovich", "19910824-0026" ,"00458793", "1249328034", "Belgium, Saudi Arabia, Poland, Turkey, USA" };
	my_passport.Output();
}
