<script lang="ts">
  import { ProjectCard } from '$lib';
	import { Anchor, Container, Box, Divider, Flex, Group, Stack, Text, ThemeIcon, Title, SimpleGrid } from '@svelteuidev/core';
	import type { Project } from '../app';
  import { AiFillGithub, AiFillLinkedin, AiFillPhone, AiFillMail } from "svelte-icons-pack/ai";
  import { Icon } from 'svelte-icons-pack';

  const projects: Project[] = [
    {
      title: 'Simple Real estate web',
      description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Phasellus egestas elit at finibus lacinia. Proin accumsan, felis a ultrices feugiat, dui ante sagittis elit, quis convallis sem augue eget neque. Mauris elementum, sapien eu venenatis efficitur, urna nisl viverra elit, nec fringilla enim eros eget dolor. Donec ac lorem nec ex ullamcorper lobortis id at justo. Sed sollicitudin gravida orci sit amet pellentesque. Donec quis leo nec lorem mattis facilisis sed eget nisl. Maecenas non elit ornare, finibus tortor sed, pharetra justo. Nam faucibus fringilla viverra. Integer fermentum nisi sit amet nibh commodo, quis ornare metus tincidunt. Sed maximus finibus magna.',
      imageSrc: 'images/realestate-preview.webp',
      link: '#',
      githubLink: 'https://github.com/Androbar/real-estate-manager',
      technologies: ['React', 'Typescript', 'Next.js', 'Chakra ui', 'Postgres', 'Prisma', 'React hook forms', 'React Query']
    },
    {
      title: 'Private chat',
      description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Phasellus egestas elit at finibus lacinia. Proin accumsan, felis a ultrices feugiat, dui ante sagittis elit, quis convallis sem augue eget neque. Mauris elementum, sapien eu venenatis efficitur, urna nisl viverra elit, nec fringilla enim eros eget dolor. Donec ac lorem nec ex ullamcorper lobortis id at justo. Sed sollicitudin gravida orci sit amet pellentesque. Donec quis leo nec lorem mattis facilisis sed eget nisl. Maecenas non elit ornare, finibus tortor sed, pharetra justo. Nam faucibus fringilla viverra. Integer fermentum nisi sit amet nibh commodo, quis ornare metus tincidunt. Sed maximus finibus magna.',
      imageSrc: 'images/private-chat.webp',
      link: '#',
      githubLink: 'https://github.com/Androbar/private-chat',
      technologies: ['React', 'Typescript', 'Next.js', 'Chakra Ui', 'Redis', 'Socket.io', 'Docker compose']
    }
  ];
</script>

<svelte:head>
  <title>Andob.ar</title>
</svelte:head>

<Box root="main">
  <Box root="section" css={{
    backgroundColor: "AliceBlue",
    color: "white",
    padding: "50px 20px",
    textAlign: "center",
  }}>
    <Container size={"xl"}>
      <Box css={{marginBottom: 16}}>
        <Title css={{marginBottom: 8}} order={1}>Andrés Arias</Title>
        <Text size="xl">Sr. Full Stack Software Engineer</Text>
        <Text size="lg">Based on Salta, Argentina</Text>
      </Box>
      <Stack gap="md">
        <Group>
          <ThemeIcon>
            <Icon src={AiFillMail} />
          </ThemeIcon>
          <Text>Mail: <Anchor href="mailto:andresrarias@gmail.com">andresrarias@gmail.com</Anchor></Text>
        </Group>
        <!-- <Group>
          <ThemeIcon>
            <Icon src={AiFillPhone} />
          </ThemeIcon>
          <Text>Phone number: <Anchor href="tel:+543876305969">+543876305969</Anchor></Text>
        </Group> -->
        <Group>
          <ThemeIcon>
            <Icon src={AiFillGithub} />
          </ThemeIcon>
          <Text>Main github account: <Anchor target="_blank" href="https://github.com/Androbas">https://github.com/Androbas</Anchor></Text>
        </Group>
        <Group>
          <ThemeIcon>
            <Icon src={AiFillGithub} />
          </ThemeIcon>
          <Text>Secondary github account: <Anchor target="_blank" href="https://github.com/Androbar">https://github.com/Androbar</Anchor></Text>
        </Group>
        <Group>
          <ThemeIcon>
            <Icon src={AiFillLinkedin} />
          </ThemeIcon>
          <Text><Anchor target="_blank" href="https://www.linkedin.com/in/andres-arias-754517177/">LinkedIn account</Anchor></Text>
        </Group>
      </Stack>
    </Container>
  </Box>

   <Box root="section" css={{ marginTop: "50px" }}>
    <Container size={"xl"}>
      <Stack gap={4}>
        <Text size="lg" css={{lineHeight: "1.4"}}>
          I'm a versatile full stack developer with over 5 years of experience in designing, developing, and managing complex software projects. My expertise spans across various technologies including Python, PostgreSQL, Javascript, ReactJS, and Next.js. I thrive in collaborative environments and take pride in delivering high-quality work that makes a lasting impact.
        </Text>
        <Text size="lg" css={{lineHeight: "1.4"}}>
          Most of my professional work is proprietary to my employers, so I am unable to showcase it here. However, I have created a few sample projects to demonstrate my skills and what I can bring to your team.
        </Text>
      </Stack>
    </Container>
  </Box>

  <Divider />

  <Box root="section" css={{ marginTop: "50px", marginBottom: "20px" }}>
    <Container size={"xl"}>
      <Title order={2}>Sample Projects</Title>
    </Container>
  </Box>

  <Box root="section">
    <Container size={"xl"}>
      <SimpleGrid
        cols={2}
        spacing={'md'}
        breakpoints={[{ maxWidth: 980, cols: 1}]}
      >
        {#each projects as project}
          <ProjectCard {project} />
        {/each}
      </SimpleGrid>
    </Container>
  </Box>
</Box>

