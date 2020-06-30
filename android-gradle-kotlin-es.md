1. Añade el repositorio de EMMA al fichero /app/build.gradle

   ```groovy
   repositories {
       maven { url 'https://repo.emma.io/emma' }
   }
   ```

2. En ese mismo fichero, añade la dependencia de EMMA a la sección de dependencias

   ```groovy
   dependencies {
       implementation 'io.emma:eMMaSDK:4.7.+'
   }
   ```

3. Importa el SDK en la clase Application e inicia sessión en EMMA

   ```kotlin
   import io.emma.android.EMMA;

   class MyApplication: Application() {

      override fun onCreate() {
           super.onCreate();

           val configuration = EMMA.Configuration.Builder(this)
               .setSessionKey("%%%SESSION_KEY%%%")
               .build();

           EMMA.getInstance().startSession(configuration);
       }
   }
   ```
