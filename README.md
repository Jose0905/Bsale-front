# Proceso en Back

Documentacion proyecto tienda Bsale

## importarcion de express

importar libreria express creando una constante aplicando destructuracion de obejtos 'request' y 'response'

importar libreria mysql proporcionada por Bsale creando una constante 

## Puerto de acceso

por medio de la constantes 'port' se accede al puerto

## crear conexion a la base de datos

Se crea conexion a abse de datos y se incluyen datos necesarios ara el ingreso, siento estos los siguientes:
    
    host     : 'mdb-test.c6vunyturrl6.us-west-1.rds.amazonaws.com',
    port     : '3306',
    user     : 'bsale_test',
    password : 'bsale_test',
    database : 'bsale_test'
   

## Conectar a la base de datos

Para conectar a la base de datos se ocupa el metodo connect y por medio de un condicional nos indicara si hubo un error y cual fue o si la conexin fue creada con exito por medio de un console.log

## inicializar la aplicacion

    const app = express();
    
## Configurar los CORS

    app.use((req, res, next) => {
	res.header('Access-Control-Allow-Origin', '*');
	res.header('Access-Control-Allow-Headers', 'Authorization, X-API-KEY, Origin, 	X-Requested-With, Content-Type, Accept, Access-Control-Allow-Request-	Method');
	res.header('Access-Control-Allow-Methods', 'GET, POST, OPTIONS, PUT, 	DELETE');
	res.header('Allow', 'GET, POST, OPTIONS, PUT, DELETE');
	next();
    });

## Administrador de rutas

	const router = express.Router();
	
## Obtener listados de la base de datos

por cada ruta (`router`) se obtiene la tabla completa de la base de datos dependiendo de la categoria a seleccionar, de no encontrarse, se indicara un error en consola

## Agregar administrador de rutas
	
	app.use(router);
	
## Evento que escucha la aplicacion

	app.listen(port, ()=>{
    	console.log("Backend corriendo en el puerto ", port);	
	});

# Proceso del Front

Luego de hacer DEPLOY del back en heroku, ingresamos el link en una constante lamada HOST,
tambien se crea la constante con lso endspoints, los cuales se iran concatenando con la variable host para obtener lo solicitado por el usuario

## Obtener listadod e categorias

Se crean las funciones `getCategorias`, `getProductos`,`getProductosIdCategoria` y `getProductosNombre` por las cuales se podran obtener por medios de un fetch y .then lo solicitado por el usuario en el buscador o el dropdown.

## Pintar en HTML

por medio de las funciones `desplegarCategorias` y `desplegarProductos` se iran agregando los producos solicitados por el usuario al html, siendo estos agregados por medio de un bucle forEach y el metodo `CreateElement`


