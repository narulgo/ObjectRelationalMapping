python = Language(name="Python", creator="Guido van Rossum", paradigm="Object-oriented and structured programming")

python.save()

ruby = Language(name="Ruby", creator="Yukihiro Matsumoto", paradigm="Object-oriented")

ruby.save()

company1=Company(name="name_Company1", location="location_Company1")

company1.save()

company2=Company(name="name_Company2", location="location_Company2")

company2.save()

programmer1 = Programmer(name="Name", age=18, company=company1)

programmer1.save()

programmer2 = Programmer(name="Name2", age=27, company=company2)

programmer2.save()

Programmer.objects.filter(company=company2)

programmer1.languages.add(python)

programmer2.languages.add(ruby)

Programmer.objects.filter(languages=ruby)

Programmer.objects.filter(languages=python)

Programmer.objects.filter(languages=python) | Programmer.objects.filter(name__icontains='Name2')
Programmer.objects.filter(languages=python) | Programmer.objects.filter(name__icontains='Name1')

Programmer.objects.filter(name__icontains='Name2').update(name='Name1')
Programmer.objects.filter(name__icontains='Name')


