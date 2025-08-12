CREATE TABLE IF NOT EXISTS type_transaction (
	id_status SERIAL UNIQUE PRIMARY KEY,
	status VARCHAR(150) NOT NULL
);

CREATE TABLE IF NOT EXISTS transaction_status (
	id_status SERIAL UNIQUE PRIMARY KEY,
	status VARCHAR(150) NOT NULL
);

CREATE TABLE IF NOT EXISTS finantial_institution(
	id_finantial_institution SERIAL UNIQUE PRIMARY KEY,
	finantial_institution VARCHAR(255) NOT NULL
);

CREATE TABLE IF NOT EXISTS type_of_currency (
	id_type_currency SERIAL UNIQUE PRIMARY KEY,
	type_currency VARCHAR(150) NOT NULL
);


CREATE TABLE IF NOT EXISTS type_identification(
	id_type_identification SERIAL UNIQUE PRIMARY KEY,
	type_idenfication VARCHAR(150) NOT NULL
);

CREATE TABLE IF NOT EXISTS users (
	id_client SERIAL,
	name_client VARCHAR(255) NOT NULL,
	identification VARCHAR(100) NOT NULL UNIQUE,
	fk_type_identification INT
		CONSTRAINT fk_type_identification
		FOREIGN KEY (id_type_identification) REFERENCES 
		type_identification(id_type_identification)
		ON DELETE CASCADE
		ON UPDATE CASCADE
);



# 1. clone repo 
https://github.com/Luis-Ortega-Coder/prueba-modulo-4-.git

# 2. write this command on t

CREATE TABLE IF NOT EXISTS type_transaction (
	id_status SERIAL UNIQUE PRIMARY KEY,
	status VARCHAR(150) NOT NULL
);

CREATE TABLE IF NOT EXISTS transaction_status (
	id_status SERIAL UNIQUE PRIMARY KEY,
	status VARCHAR(150) NOT NULL
);

CREATE TABLE IF NOT EXISTS finantial_institution(
	id_finantial_institution SERIAL UNIQUE PRIMARY KEY,
	finantial_institution VARCHAR(255) NOT NULL
);

CREATE TABLE IF NOT EXISTS type_of_currency (
	id_type_currency SERIAL UNIQUE PRIMARY KEY,
	type_currency VARCHAR(150) NOT NULL
);


CREATE TABLE IF NOT EXISTS type_identification(
	id_type_identification SERIAL UNIQUE PRIMARY KEY,
	type_idenfication VARCHAR(150) NOT NULL
);

CREATE TABLE IF NOT EXISTS users (
	id_client SERIAL PRIMARY KEY,
	name_client VARCHAR(255) NOT NULL,
	identification VARCHAR(100) NOT NULL UNIQUE,
	fk_type_identification INT,
	FOREIGN KEY (fk_type_identification) REFERENCES type_identification(id_type_identification)
				ON DELETE CASCADE
				ON UPDATE CASCADE,
	address VARCHAR(255) NOT NULL,
	phone VARCHAR(150) NOT NULL,
	email VARCHAR(120) NOT NULL
);

CREATE TABLE billing (
	id_billing VARCHAR(30) NOT NULL UNIQUE,
	date_billing TIMESTAMP NOT NULL,
	id_identificate_client VARCHAR(100),
	FOREIGN KEY (id_identificate_client) REFERENCES users(identification)
		ON DELETE CASCADE
		ON UPDATE CASCADE,
	id_financial_institution INT NOT NULL,
	FOREIGN KEY (id_finanti)
);