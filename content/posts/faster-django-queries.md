+++
title = 'Faster Django Queries'
date = 2022-12-07
draft = false
tags = ['python', 'django']
Description = 'Improve your django queries'
+++

## Analyze your queries

To see all interactions with the database:

In the `settings.py` add the code below to store all interactions in the sql.log file.
```py
LOGGING = {
	'version': 1,
	'disable_existing_loggers': False,
	'handlers': {
		'file': {
			'level: 'DEBUG',
			'class': 'logging.FileHandlers',
			'filename': 'sql.log',
		},
	},
	'loggers': {
		'django.db.backends': {
			'handlers': ['files'],
			'levels': 'DEBUG',
			'propagate': 'TRUE'
		}
	}
}

```

#### Tip 1: Use bulk insert
```py
students = []  
grades = []  
batch_size = 500  
for i in range(1000):  
	student = Student()  
	student.first_name = str(i)  
	student.last_name = str(i)  
	students.append(student)  
Student.objects.bulk_create(students, batch_size)
```

#### Tip 2: Use bulk update
```py
batch_size = 500  
grades = Grade.objects.all()  
for grade in grades:  
	grade.grade = 100  
Grade.objects.bulk_update(grades, [**'grade'**], batch_size=batch_size)
```

#### Tip 3: Preload related object data
```py
grades = Grade.objects.select_related("student").all()  
for grade in grades:  
	print(f"The student {grade.student.first_name} has got 
          {grade.grade}%")
```

#### Tip 4: Select in bulk
```py
ids = []  
grades = Grade.objects.all()  
for grade in grades:  
	if grade.grade == 100:  
		ids.append(grade.student_id)  
students = Student.objects.in_bulk(ids)  
for student in students:  
	print(student.first_name, student.last_name)
```