# Быстрый старт
```json
{  
	"compilerOptions": {    
		/* Базовые опции: */   
		"esModuleInterop": true,   
		"skipLibCheck": true,   
		"target": "es2022",    
		"allowJs": true,    
		"resolveJsonModule": true,    
		"moduleDetection": "force",    
		"isolatedModules": true,    
		/* Строгость */    
		"strict": true,    
		"noUncheckedIndexedAccess": true,    
		/* Если транспилируете с TypeScript: */    
		"moduleResolution": "NodeNext",    
		"module": "NodeNext",    
		"outDir": "dist",    
		"sourceMap": true,    
		/* А если вы собираете для библиотеки: */    
		"declaration": true,    
		/* А если вы собираете для библиотеки в монорепо: */    
		"composite": true,    
		"declarationMap": true,    
		/* Если НЕ транспилируете с TypeScript: */    
		"moduleResolution": "Bundler",    
		"module": "preserve",    
		"noEmit": true,    
		/* Если ваш код запускается в DOM: */    
		"lib": ["es2022", "dom", "dom.iterable"],    
		/* Если ваш код не запускается в DOM: */    
		"lib": ["es2022"]  
	}
}
```

[Подробности на dev-notes](https://www.dev-notes.ru/articles/typescript/tsconfig-cheat-sheet/)

